# Telegraf - Loki 

This repository represents a error case while connecting telegraf logs from docker_log to loki.
It is ment as a proof of concept in order to ask for help, currently the loki server response with 400: Bad Request error as seen in telegraf log.

Accessing the loki Container with curl http://loki:3100/ready replies with "ready" state.

Example Startup Logs available in [loki](_loki_logs.txt) [telegraf](_telegraf_logs.txt)

If you know the cause of this please reach out via issue / pull request.
