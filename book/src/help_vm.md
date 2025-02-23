# Validator Manager

```
Utilities for managing a Lighthouse validator client via the HTTP API.

Usage: lighthouse validator_manager [OPTIONS] [COMMAND]

Commands:
  create
          Creates new validators from BIP-39 mnemonic. A JSON file will be
          created which contains all the validator keystores and other validator
          data. This file can then be imported to a validator client using the
          "import-validators" command. Another, optional JSON file is created
          which contains a list of validator deposits in the same format as the
          "ethereum/staking-deposit-cli" tool.
  import
          Uploads validators to a validator client using the HTTP API. The
          validators are defined in a JSON file which can be generated using the
          "create-validators" command.
  move
          Uploads validators to a validator client using the HTTP API. The
          validators are defined in a JSON file which can be generated using the
          "create-validators" command. This command only supports validators
          signing via a keystore on the local file system (i.e., not Web3Signer
          validators).
  list
          Lists all validators in a validator client using the HTTP API.
  delete
          Deletes one or more validators from a validator client using the HTTP
          API.
  help
          Print this message or the help of the given subcommand(s)

Options:
  -d, --datadir <DIR>
          Used to specify a custom root data directory for lighthouse keys and
          databases. Defaults to $HOME/.lighthouse/{network} where network is
          the value of the `network` flag Note: Users should specify separate
          custom datadirs for different networks.
      --debug-level <LEVEL>
          Specifies the verbosity level used when emitting logs to the terminal.
          [default: info] [possible values: info, debug, trace, warn, error,
          crit]
      --genesis-state-url <URL>
          A URL of a beacon-API compatible server from which to download the
          genesis state. Checkpoint sync server URLs can generally be used with
          this flag. If not supplied, a default URL or the --checkpoint-sync-url
          may be used. If the genesis state is already included in this binary
          then this value will be ignored.
      --genesis-state-url-timeout <SECONDS>
          The timeout in seconds for the request to --genesis-state-url.
          [default: 180]
      --log-format <FORMAT>
          Specifies the log format used when emitting logs to the terminal.
          [possible values: JSON]
      --logfile <FILE>
          File path where the log file will be stored. Once it grows to the
          value specified in `--logfile-max-size` a new log file is generated
          where future logs are stored. Once the number of log files exceeds the
          value specified in `--logfile-max-number` the oldest log file will be
          overwritten.
      --logfile-debug-level <LEVEL>
          The verbosity level used when emitting logs to the log file. [default:
          debug] [possible values: info, debug, trace, warn, error, crit]
      --logfile-format <FORMAT>
          Specifies the log format used when emitting logs to the logfile.
          [possible values: DEFAULT, JSON]
      --logfile-max-number <COUNT>
          The maximum number of log files that will be stored. If set to 0,
          background file logging is disabled. [default: 10]
      --logfile-max-size <SIZE>
          The maximum size (in MB) each log file can grow to before rotating. If
          set to 0, background file logging is disabled. [default: 200]
      --network <network>
          Name of the Eth2 chain Lighthouse will sync and follow. [possible
          values: mainnet, gnosis, chiado, sepolia, holesky]
  -t, --testnet-dir <DIR>
          Path to directory containing eth2_testnet specs. Defaults to a
          hard-coded Lighthouse testnet. Only effective if there is no existing
          database.

Flags:
      --disable-log-timestamp
          If present, do not include timestamps in logging output.
      --disable-malloc-tuning
          If present, do not configure the system allocator. Providing this flag
          will generally increase memory usage, it should only be provided when
          debugging specific memory allocation issues.
  -h, --help
          Prints help information
      --log-color
          Force outputting colors when emitting logs to the terminal.
      --logfile-compress
          If present, compress old log files. This can help reduce the space
          needed to store old logs.
      --logfile-no-restricted-perms
          If present, log files will be generated as world-readable meaning they
          can be read by any user on the machine. Note that logs can often
          contain sensitive information about your validator and so this flag
          should be used with caution. For Windows users, the log file
          permissions will be inherited from the parent folder.
      --stdin-inputs
          If present, read all user inputs from stdin instead of tty.
```

<style> .content main {max-width:88%;} </style>
