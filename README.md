# dex-arb

## uniswap v3 function 
Contract address：0x68b3465833fb72a70ecdf485e0e4c7bd8665fc45

```
{
  approveMax: [ 'address' ],
  approveMaxMinusOne: [ 'address' ],
  approveZeroThenMax: [ 'address' ],
  approveZeroThenMaxMinusOne: [ 'address' ],
  callPositionManager: [ 'bytes' ],
  checkOracleSlippage: [ 'bytes', 'uint24', 'uint32' ],
  exactInput: [ 'bytes', 'address', 'uint256', 'uint256' ],
  exactInputSingle: [
    'address', 'address',
    'uint24',  'address',
    'uint256', 'uint256',
    'uint160'
  ],
  exactOutput: [ 'bytes', 'address', 'uint256', 'uint256' ],
  exactOutputSingle: [
    'address', 'address',
    'uint24',  'address',
    'uint256', 'uint256',
    'uint160'
  ],
  getApprovalType: [ 'address', 'uint256' ],
  increaseLiquidity: [ 'address', 'address', 'uint256', 'uint256', 'uint256' ],
  mint: [
    'address', 'address',
    'uint24',  'int24',
    'int24',   'uint256',
    'uint256', 'address'
  ],
  multicall: [ 'bytes[]' ],
  pull: [ 'address', 'uint256' ],
  selfPermit: [ 'address', 'uint256', 'uint256', 'uint8', 'bytes32', 'bytes32' ],
  selfPermitAllowed: [ 'address', 'uint256', 'uint256', 'uint8', 'bytes32', 'bytes32' ],
  selfPermitAllowedIfNecessary: [ 'address', 'uint256', 'uint256', 'uint8', 'bytes32', 'bytes32' ],
  selfPermitIfNecessary: [ 'address', 'uint256', 'uint256', 'uint8', 'bytes32', 'bytes32' ],
  swapExactTokensForTokens: [ 'uint256', 'uint256', 'address[]', 'address' ],
  swapTokensForExactTokens: [ 'uint256', 'uint256', 'address[]', 'address' ],
  sweepToken: [ 'address', 'uint256' ],
  sweepTokenWithFee: [ 'address', 'uint256', 'address', 'uint256', 'address' ],
  uniswapV3SwapCallback: [ 'int256', 'int256', 'bytes' ],
  unwrapWETH9: [ 'uint256' ],
  unwrapWETH9WithFee: [ 'uint256', 'uint256', 'address' ],
  wrapETH: [ 'uint256' ]
}
```

## Function Signature
```
{
  '0x571ac8b0': 'approveMax(address)',
  '0xcab372ce': 'approveMaxMinusOne(address)',
  '0x639d71a9': 'approveZeroThenMax(address)',
  '0xab3fdd50': 'approveZeroThenMaxMinusOne(address)',
  '0xb3a2af13': 'callPositionManager(bytes)',
  '0xf25801a7': 'checkOracleSlippage(bytes,uint24,uint32)',
  '0x11b69c46': 'exactInput(bytes,address,uint256,uint256)',
  '0xd7353b07': 'exactInputSingle(address,address,uint24,address,uint256,uint256,uint160)',
  '0x28c2250a': 'exactOutput(bytes,address,uint256,uint256)',
  '0x6ed1e2e4': 'exactOutputSingle(address,address,uint24,address,uint256,uint256,uint160)',
  '0xdee00f35': 'getApprovalType(address,uint256)',
  '0xb93bdd91': 'increaseLiquidity(address,address,uint256,uint256,uint256)',
  '0x369d12c2': 'mint(address,address,uint24,int24,int24,uint256,uint256,address)',
  '0xac9650d8': 'multicall(bytes[])',
  '0xf2d5d56b': 'pull(address,uint256)',
  '0xf3995c67': 'selfPermit(address,uint256,uint256,uint8,bytes32,bytes32)',
  '0x4659a494': 'selfPermitAllowed(address,uint256,uint256,uint8,bytes32,bytes32)',
  '0xa4a78f0c': 'selfPermitAllowedIfNecessary(address,uint256,uint256,uint8,bytes32,bytes32)',
  '0xc2e3140a': 'selfPermitIfNecessary(address,uint256,uint256,uint8,bytes32,bytes32)',
  '0x472b43f3': 'swapExactTokensForTokens(uint256,uint256,address[],address)',
  '0x42712a67': 'swapTokensForExactTokens(uint256,uint256,address[],address)',
  '0xe90a182f': 'sweepToken(address,uint256)',
  '0xe0e189a0': 'sweepTokenWithFee(address,uint256,address,uint256,address)',
  '0xfa461e33': 'uniswapV3SwapCallback(int256,int256,bytes)',
  '0x49616997': 'unwrapWETH9(uint256)',
  '0xd4ef38de': 'unwrapWETH9WithFee(uint256,uint256,address)',
  '0x1c58db4f': 'wrapETH(uint256)'
}
```

## How to decode uniswap v3 calldata
1. get input data from `provider.getTransaction(hash)`
2. use [abi-decoder](https://github.com/ConsenSys/abi-decoder) decode the input_data to get `name` and `params`
3. if name === multicall, then decode with `web3.eth.abi.decodeParameters`
