# Upgrade from v4.x to v5.0

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

- If you have a question regarding this upgrade process, please check code in `examples` directory:

* [Complete Application Load Balancer](https://github.com/nholuongut/terraform-aws-alb/tree/master/examples/complete-alb)
* [Complete Network Load Balancer](https://github.com/nholuongut/terraform-aws-alb/tree/master/examples/complete-nlb)

If you found a bug, please open an issue in this repository.

## List of backward incompatible changes

### Removed resources

1. Removed resources:

    - aws_lb.application_no_logs
    - aws_lb_target_group.main_no_logs
    - aws_lb_listener.frontend_http_tcp_no_logs
    - aws_lb_listener.frontend_https_no_logs
    - aws_lb_listener_certificate.https_listener_no_logs

   If you've been using ALB without access logs enabled then you need to run `terraform state mv` to rename resources to new names:

    - aws_lb.this
    - aws_lb_target_group.main
    - aws_lb_listener.frontend_http_tcp
    - aws_lb_listener.frontend_https
    - aws_lb_listener_certificate.https_listener

   For example, this command will rename ALB resource: `terraform state mv aws_lb.application_no_logs aws_lb.this`

2. Removed variable `target_groups_count`, `http_tcp_listeners_count`, `extra_ssl_certs_count`, `http_tcp_listeners_count`.

3. Removed variable `target_groups_defaults`. Instead, all `health_check` and `stickiness` settings should be implicit for each target group.

# Renamed variables and outputs

1. Renamed logging variables `logging_enabled`, `log_bucket_name`, `log_location_prefix` into a map `access_logs` with keys `enabled`, `bucket`, `prefix`.

2. Renamed variables:

   - `load_balancer_name` => `name`
   - `load_balancer_is_internal` => `internal`
   - `create_alb` => `create_lb`

3. Renamed outputs:

   - `load_balancer_id` => `this_lb_id`
   - `dns_name` => `this_lb_dns_name`
  
# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)