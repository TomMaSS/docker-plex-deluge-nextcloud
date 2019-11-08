FROM centos:latest

#install crontabs
RUN yum -y install epel-release \
 && yum -y install crontabs \
 && yum -y install nextcloud-client \
 && yum -y install less

# comment out PAM
RUN sed -i -e '/pam_loginuid.so/s/^/#/' /etc/pam.d/crond

#Add nxcl credential file
#ADD myncs.conf /etc/myncs.conf

#Add cron file
ADD ./cron_nxt_cld /etc/cron.d/cron_nxt_cld
RUN chmod 0644 /etc/cron.d/cron_nxt_cld

#Add nexctcloud client sync script
ADD nextcloud-sync-cron.sh /opt/nextcloud-sync-cron.sh

#This will add it to the cron table (crontab -e)
RUN crontab /etc/cron.d/cron_nxt_cld

CMD crond && tail -f /dev/null