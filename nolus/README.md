### Nolus Snapshot Setup
You can browse the logs for current snapshot date, block height, and file size information.

*height: 1282011 (6h ago) | size: 19gb | pruning: nothing: 100/0/10 | indexer: null*


#### Stop node
`sudo systemctl stop defundd`
#### Save backup priv_validator_state
`cp $HOME/.defund/data/priv_validator_state.json` `$HOME/.defund/priv_validator_state.json.backup`
#### Delete data and download snapshot
`rm -rf $HOME/.defund/data $HOME/.defund/wasm`
`curl http://195.201.237.185/nolus/nolus-rila_latest.tar | tar -xf - -C $HOME/.defund`
#### Restote backup priv_validator_state
`mv $HOME/.defund/priv_validator_state.json.backup` `$HOME/.defund/data/priv_validator_state.json`
#### Start node and check the logs
`sudo systemctl restart defundd && sudo journalctl -u defundd -f`
