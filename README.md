# sysbench-release

Provides `sysbench` functionality via two jobs:

- `sysbench` to benchmark CPU/disk/memory
  - Example: [manifests/example.yml](manifests/example.yml)
  - `bosh -d sysbench run-errand sysbench`

- `sysbench_oltp` to benchmark database performance
  - Example: [manifests/example-oltp.yml](manifests/example-oltp.yml)
  - `bosh -d sysbench run-errand sysbench_oltp`
  - Includes `/var/vcap/jobs/sysbench_oltp/bin/mysql` client for convenience

Both jobs include few default benchmarks in their spec files.

Note: Packages use `apt-get install` to install `sysbench` and `mysql-client`, hence if you need an internetless release use [`bosh export release` command](https://bosh.io/docs/compiled-releases).

This release was made to benchmark https://github.com/cppforlife/tidb-release.

## Resources

- [docs/errors.md](docs/errors.md)
- http://manpages.ubuntu.com/manpages/xenial/man1/sysbench.1.html
- http://benchmark-docs.readthedocs.io/en/latest/index.html
