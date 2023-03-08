### Nolus Snapshot Setup
You can browse the logs for current snapshot date, block height, and file size information.

*height: 1282011 (6h ago) | size: 19gb | pruning: nothing: 100/0/10 | indexer: null*


#### Stop node
`sudo systemctl stop nolusd`
#### Save backup priv_validator_state
`cp $HOME/.nolusd/data/priv_validator_state.json` `$HOME/.nolusd/priv_validator_state.json.backup`
#### Delete data and download snapshot
`rm -rf $HOME/.nolusd/data $HOME/.nolusd/wasm`
`curl http://195.201.237.185/nolus/nolus-rila_latest.tar | tar -xf - -C $HOME/.defund`
#### Restote backup priv_validator_state
`mv $HOME/.nolusd/priv_validator_state.json.backup` `$HOME/.nolusd/data/priv_validator_state.json`
#### Start node and check the logs
`sudo systemctl restart nolusd && sudo journalctl -u nolusd -f`
