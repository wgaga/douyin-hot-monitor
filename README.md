name: 抖音爆款监控-定时触发
on:
  schedule:
    - cron: '0 * * * *'
  workflow_dispatch: # 这一行必须加上，否则手动运行按钮不会出现！

jobs:
  trigger-workflow:
    runs-on: ubuntu-latest
    steps:
      - name: 调用扣子工作流API
        run: |
          curl -X POST 'https://api.coze.cn/v1/workflow/stream_run' \
          -H 'Authorization: Bearer cztei_0c8466841d05482d88194e99d705466d' \
          -H 'Content-Type: application/json' \
          -d '{"workflow_id": "7624589607500769320","app_id": "7624589607500769320","parameters": {"input": "抖音爆款监控自动触发"}}'
