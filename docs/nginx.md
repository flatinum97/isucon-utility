# Nginx

## Logging
alpに対応させたフォーマットに変更する

```nginx.conf
http {
  log_format ltsv "time:$time_iso8601"
    "\tremote_addr:$remote_addr"
    "\thost:$host"
    "\http_x_forwarded_for:$http_x_forwarded_for"
    "\trequest:$request"
    "\tmethod:$request_method"
    "\turi:$request_uri"
    "\tstatus:$status"
    "\tsize:$body_bytes_sent"
    "\treferer:$http_referer"
    "\tua:$http_user_agent"
    "\trequest_time:$request_time"
    "\truntime:$upstream_http_x_runtime"
    "\tupstream_response_time:$upstream_response_time"
    "\tupstream_status:$upstream_status"
    "\tcache:$upstream_http_x_cache";

    access_log  /var/log/nginx/access.log ltsv;
}
```
