This project provides a performance comparison for Java dependency cache mechanism.
Refer to https://github.com/actions/setup-java/pull/193 for the context.

## About the test

See workflow files in the `.github/workflows` directory. There is tests that compares the elapsed time of:

1. run JDK set up and dependency caching sequential (`actions/setup-java` and `actions/cache`)
2. run JDK set up and dependency caching in parallel (new feature suggested by the PR)

In the `report` job of each workflow, GitHub Actions prints a CSV like below:

```csv
type,elapsed[ms]
parallel,2379
parallel,4031
parallel,1974
parallel,2208
parallel,4567
parallel,2251
parallel,2247
parallel,5829
parallel,6593
parallel,10647
sequential,6607
sequential,4089
sequential,5671
sequential,3460
sequential,43331
sequential,2351
sequential,4231
sequential,2894
sequential,3687
sequential,3190
```

