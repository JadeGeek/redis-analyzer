# Memory Analyzer

## Usage

```
# redis-analyzer --help

redis-analyzer 0.1.0
Analyzes keys in Redis to produce breakdown of the most frequent prefixes.

USAGE:
    redis-analyzer [OPTIONS] --urls <URLS>

FLAGS:
    -h, --help       Prints help information
    -V, --version    Prints version information

OPTIONS:
    -d, --max-depth <MAX_DEPTH>                                     Maximum key depth to examine (default: not limited)
    -p, --max-parallelism <MAX_PARALLELISM>
            Maximum number of hosts scanned at the same time (default: number of logical CPUs)

    -f, --min-prefix-frequency <MIN_PREFIX_FREQUENCY_PERCENTAGE>    Minimum prefix frequency in percentages for prefix to be included in the result (default: 1)
    -s, --separators <SEPARATORS>                                   List of key separators (default: ":/|" )
    -u, --urls <URLS>
```

## Preview

![preview](preview.gif)

Example output:

```
root => count: 1193, size: 12.42 MB (100.00%)
  cache => count: 294, size: 2.14 MB (17.25%)
    cache:rails5.1.6 => count: 13, size: 1.16 MB (54.11%)
      cache:rails5.1.6/trends => count: 13, size: 1.16 MB (100.00%)
        cache:rails5.1.6/trends/v1 => count: 13, size: 1.16 MB (100.00%)
    cache:rails5.2.2 => count: 13, size: 957.75 kB (44.70%)
      cache:rails5.2.2/trends => count: 13, size: 957.75 kB (100.00%)
        cache:rails5.2.2/trends/v1 => count: 13, size: 957.75 kB (100.00%)
    cache:Touchify => count: 239, size: 21.12 kB (0.99%)
      cache:Touchify/internal => count: 239, size: 21.12 kB (100.00%)
        cache:Touchify/internal/User => count: 239, size: 21.12 kB (100.00%)
  feed => count: 158, size: 1.68 MB (13.55%)
    feed:feed => count: 158, size: 1.68 MB (100.00%)
      feed:feed/feeds => count: 155, size: 1.68 MB (99.93%)
  sidekiq => count: 429, size: 1.51 MB (12.20%)
    sidekiq:sidekiq-scheduler => count: 27, size: 188.29 kB (12.43%)
      sidekiq:sidekiq-scheduler:pushed => count: 25, size: 184.44 kB (97.95%)
      other => count: 2, size: 3.85 kB (2.05%)
    sidekiq:stat => count: 388, size: 28.88 kB (1.91%)
      sidekiq:stat:processed => count: 194, size: 14.93 kB (51.68%)
      sidekiq:stat:failed => count: 194, size: 13.96 kB (48.32%)
    other => count: 14, size: 1.3 MB (85.66%)
  notifications => count: 75, size: 637.51 kB (5.13%)
    notifications:feed => count: 74, size: 637.41 kB (99.98%)
      notifications:feed/feeds => count: 71, size: 636.73 kB (99.89%)
  store => count: 47, size: 209.62 kB (1.69%)
    store:recommendation_service => count: 13, size: 1.29 kB (0.61%)
    other => count: 34, size: 208.34 kB (99.39%)
  adstats => count: 41, size: 10.34 kB (0.08%)
    adstats:ads => count: 41, size: 10.34 kB (100.00%)
      adstats:ads/stats => count: 36, size: 8.95 kB (86.55%)
      other => count: 5, size: 1.39 kB (13.45%)
  counts => count: 120, size: 9.92 kB (0.08%)
    counts:CountsService => count: 120, size: 9.92 kB (100.00%)
      counts:CountsService/User => count: 120, size: 9.92 kB (100.00%)
  rollout => count: 27, size: 2.53 kB (0.02%)
    rollout:feature => count: 27, size: 2.53 kB (100.00%)
  other => count: 2, size: 6.21 MB (50.00%)
```