random
======
create view wz_content_control as select us.user_id from user_summary us
where us.user_id NOT IN (select user_id from wz_content_test)
and (user_join_date < '2014-3-16' and email_subscription_status = 'active')
or email_unsubscribe_date < '2014-3-16'
order by rand() limit 100;
