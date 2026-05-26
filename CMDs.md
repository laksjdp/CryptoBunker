## LAKS-JDP

### Install the Tools
```bash
  forge init # or -> sudo $(which forge) init\

  # Install dependencies [Install, Assign & Import OpenZeppelin contracts]
  forge install OpenZeppelin/openzeppelin-contracts --no-comit      
  # remappings=['@openzeppelin/contracts=lin/openzeppelin-contracts/contracts']
  # import {ERC20} from "@openzeppelin/contracts/token/ERC20/ERC20.sol"

  forge test      # Testing the Project
  forge build     # Build the Project
  forge inspect ContractName storage  # Check the storage
  forge coverage  # Check how much percentage testage. It must be more than 96%
  forge inspect ContractName methods  # Check Methods


  cast storage 0xContractAddress 1 --rpc-url http://127.0.0.1:8545
  cast parse-bytes32-string 0xPrivateVariableHash 

  # Get Specific committed code
  git checkout 0xCommitHash

  # Install Tools
  sudo apt install cloc           # Install cloc
  sudo apt install pipx           # Install pipx
  pipx install slither-analyzer   # Install Slither
  pipx upgrade slither-analyzer   # Upgrade the tool
  # Install Aderyn
  curl --proto '=https' --tlsv1.2 -LsSf https://github.com/cyfrin/aderyn/releases/latest/download/aderyn-installer.sh | bash
```

### Recon Flow
- ***Scoping*** - `Check the Reckt Test`
- `Get the Code`, `Read the docs`, `Read the code`
- `About the Project`, `Attack vectors`, `Check vulns`
- `Convey information to make it safer`
- [Severity Guide](https://docs.codehawks.com/hawks-auditors/how-to-evaluate-a-finding-severity)


### Testings
- `Static Analysis`, `Fuzz Testing`, `Differential Test`, `Chaos Test`
- `Formal Verification`

### Toolset
- ***Static Analysis*** - `Slither`, `aderyn`, `mythril`
- ***Fuzz Testing*** - `Stateless Fuzzing`, `Stateful Fuzzing` 
- `TL;DR`
- [Web3Bugs](https://github.com/ZhangZhuoSJTU/Web3Bugs.git)

### Extensions
- ***solidity metric*** - `Generate smart contract metrics` 
- ***Solidity visual developer*** - `For viasual appearance about which variable for what purpose`
- ***Huff***

### Notes.md
```markdown
  # About 
  > About the Project on my own

  # Informational

```