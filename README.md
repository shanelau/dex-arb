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
  '0xe8e33700': 'addLiquidity(address,address,uint256,uint256,uint256,uint256,address,uint256)',
  '0xf305d719': 'addLiquidityETH(address,uint256,uint256,uint256,address,uint256)',
  '0x85f8c259': 'getAmountIn(uint256,uint256,uint256)',
  '0x054d50d4': 'getAmountOut(uint256,uint256,uint256)',
  '0x1f00ca74': 'getAmountsIn(uint256,address[])',
  '0xd06ca61f': 'getAmountsOut(uint256,address[])',
  '0xad615dec': 'quote(uint256,uint256,uint256)',
  '0xbaa2abde': 'removeLiquidity(address,address,uint256,uint256,uint256,address,uint256)',
  '0x02751cec': 'removeLiquidityETH(address,uint256,uint256,uint256,address,uint256)',
  '0xaf2979eb': 'removeLiquidityETHSupportingFeeOnTransferTokens(address,uint256,uint256,uint256,address,uint256)',
  '0xded9382a': 'removeLiquidityETHWithPermit(address,uint256,uint256,uint256,address,uint256,bool,uint8,bytes32,bytes32)',
  '0x5b0d5984': 'removeLiquidityETHWithPermitSupportingFeeOnTransferTokens(address,uint256,uint256,uint256,address,uint256,bool,uint8,bytes32,bytes32)',
  '0x2195995c': 'removeLiquidityWithPermit(address,address,uint256,uint256,uint256,address,uint256,bool,uint8,bytes32,bytes32)',
  '0xfb3bdb41': 'swapETHForExactTokens(uint256,address[],address,uint256)',
  '0x7ff36ab5': 'swapExactETHForTokens(uint256,address[],address,uint256)',
  '0xb6f9de95': 'swapExactETHForTokensSupportingFeeOnTransferTokens(uint256,address[],address,uint256)',
  '0x18cbafe5': 'swapExactTokensForETH(uint256,uint256,address[],address,uint256)',
  '0x791ac947': 'swapExactTokensForETHSupportingFeeOnTransferTokens(uint256,uint256,address[],address,uint256)',
  '0x38ed1739': 'swapExactTokensForTokens(uint256,uint256,address[],address,uint256)',
  '0x5c11d795': 'swapExactTokensForTokensSupportingFeeOnTransferTokens(uint256,uint256,address[],address,uint256)',
  '0x4a25d94a': 'swapTokensForExactETH(uint256,uint256,address[],address,uint256)',
  '0x8803dbee': 'swapTokensForExactTokens(uint256,uint256,address[],address,uint256)'
}
```

## How to decode uniswap v3 calldata
1. get input data from `provider.getTransaction(hash)`
2. use [abi-decoder](https://github.com/ConsenSys/abi-decoder) decode the input_data to get `name` and `params`
3. if name === multicall, then decode with `web3.eth.abi.decodeParameters`
