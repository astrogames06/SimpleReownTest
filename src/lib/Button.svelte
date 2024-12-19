<script>
  import { createAppKit } from '@reown/appkit/react'
  import { SolanaAdapter } from '@reown/appkit-adapter-solana/react'
  import { solana, solanaTestnet, solanaDevnet } from '@reown/appkit/networks'
  import { PhantomWalletAdapter, SolflareWalletAdapter } from '@solana/wallet-adapter-wallets'

  // 0. Set up Solana Adapter
  const solanaWeb3JsAdapter = new SolanaAdapter({
    wallets: [new PhantomWalletAdapter(), new SolflareWalletAdapter()]
  })

  // 1. Get projectId from https://cloud.reown.com
  const projectId = 'bd9425e479238b5be58b574c55534f34'
  
  // 3. Create modal
  createAppKit({
    adapters: [solanaWeb3JsAdapter],
    networks: [solana, solanaTestnet, solanaDevnet],
    metadata: null,
    projectId,
    features: {
      email: true, // Disable email login
      socials: [],
      analytics: true // Optional - defaults to your Cloud configuration
    },
  })
</script>

<appkit-button></appkit-button>
