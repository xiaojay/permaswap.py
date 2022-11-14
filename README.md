# permaswap.py
python sdk for permaswap

# usage

1. perpare everpay account

api_server = 'https://api-dev.everpay.io'

# eth
pk = ''
signer = everpay.ETHSigner(pk)

# or ar account
#signer = everpay.ARSigner('arweave-keyfile-xxx.json')
account = everpay.Account(api_server, signer)

2. Query order

router_host = 'wss://router0-dev.permaswap.network/'
swap = permaswap.Permaswap(router_host, account)

# get_order('token_in', 'token_out', 'amount_in')
order = swap.get_order('tAR', 'tUSDC', 10**12)
print(order)

3. Place order

result = swap.place_order(order)
print(result)
