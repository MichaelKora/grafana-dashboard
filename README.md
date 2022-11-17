# Default Dashboard to monitor your Kafka Pipeline

This dashboard will allow you to monitor three specific metrics of your Kafka deployment:

- messages in per second for all topics
- lag of consumers
- dead letters per second

Make sure to add a label 'pipeline' with the same value for each app so that the dashboard can recognize which applications belong together.

```yaml
app:
    labels:
      pipeline: ${SRC_TYPE}-${SRC}
```

For the time being, set the `$ErrorSuffix` variable to the suffix of your topics handling invalid inputs in your pipeline.
By default, the Dashboard expects such a topic to have a `dead-letters` at the end of its name. If the name of your error topic differs from this, make sure to update it in the `default-dashboard.json` file.
