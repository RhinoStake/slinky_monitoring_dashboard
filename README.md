# Grafana Dashboard for Monitoring Slinky Oracle Operations

This is a work-in-progress Grafana dashboard for monitoring the [Slinky Oracle](https://github.com/skip-mev/slinky). Setting up Prometheus/Grafana is outside the scope of this repo. Use the [excellent guide from Artifact Staking](https://artifact-staking.medium.com/setting-up-validator-monitoring-for-aptos-testnet-2-85d5c4e94c80).

![slinky monitoring dashboard]((https://snapshots.rhinostake.com/dropshare/nomograph-pericardiac-fers-thunderfishes.png)

## A few assumptions and instructions for setup:

- This is in-progress and will have significant updates in 2024 as I (and other operators) better understand the important metrics and alerts for proper oracle operations.
- This requires a Prometheus data source (obviously), pulling data from the both the standard prometheus endpoint of the blockchain binary as well as the prometheus endpoint of the Slinky Oracle (by default at :9090)
- Ensure that node-exporter is installed on your Validator to pull machine metrics: `apt install prometheus-node-exporter`.
- This dashboard relies primarily on the `job` tag, assuming that both the blockchain and sidecar prometheus endpoints are tied to the same `job` tag, the metrics should flow

```yaml
# Example job in 
  - job_name: dydx
    static_configs:
      - targets: [
          "33.33.33.33:26660", # binary prom endpoint
          "33.33.33.33:9090", # slinky side car prom endpoint
          ]
```

### Additional Functionality

- TBD
- 
## How to use this file

# Preferred Option

- Utilize the all-in-one metrics and alerting solution here...


# Manual Option
- Download the `.json` file from the Grafana folder in this repository
- Hit Import in Grafana

![grafana import](https://grabup.teamhim.com/unalimentative-winterage-lucently-pharyngotonsillitis.png?raw=true)

- Click Upload JSON and select the file downloaded
- Select your Prometheus datasource from the dropdown & import!

![grafana import](https://grabup.teamhim.com/tabescence-jamshid-tiou-stinkier.png?raw-true)

Have ideas/changes/additions? Great! Feel free to push a PR to this repo or reach out to [me on Discord](https://discord.gg/SGhQzj5tyz)!

## Who is RHINO?

RHINO is a professionally managed, highly available validator service. Earn rewards and help secure networks by staking your tokens with RHINO. We operate across the Aptos, Cosmos, Chainlink, and Helium ecosystems. Read more at [https://rhinostake.com](https://rhinostake.com).
