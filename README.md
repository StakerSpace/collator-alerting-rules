# collator-monitoring-rules
Alert manager collator rules for generic substrate metrics from the prometheus stream.

Most of the rules originate from the [alerting-rules.yaml](https://raw.githubusercontent.com/paritytech/substrate/master/.maintain/monitoring/alerting-rules/alerting-rules.yaml) that are in the [substrate repo](https://github.com/paritytech/substrate).

## customization:
- Changed all of the applicable of `polkadot_` to `substrate_` metrics
- Removed the `authority_discovery` metrics as this is not applicable to collator roles
- Removed the label `{{ $labels.entity }}` as we don't know and have not configued such a label. 
- Added `increase(substrate_proposer_block_constructed_count[1h]) < 1` to the rules to warn if you haven't constructed a block in a hour time-frame.

We mainain and improve on these metrics in the future for more collator specific metrics. 
