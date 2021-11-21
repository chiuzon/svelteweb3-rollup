<script lang="ts">
	import { svelteWeb3 } from '@chiuzon/svelteweb3'
    import {WalletConnectConnector} from '@web3-react/walletconnect-connector'
import { onMount } from 'svelte';

    const { activate, error } = svelteWeb3()

    let connector = new WalletConnectConnector({ rpc: { 1: "https://mainnet.infura.io/v3/9aa3d95b3bc440fa88ea12eaa4456161" }, qrcode: true })
    // onMount(() => {
    //     connector = new WalletConnectConnector({ rpc: { 1: "https://mainnet.infura.io/v3/9aa3d95b3bc440fa88ea12eaa4456161" }, qrcode: true })

    // })

    async function conn() {
        await activate(connector, async (e) => {
            //You can ask here the user if he wanna switch networks or show a popup modal
            console.error(e)
        })
    }
</script>

<div>
    <button on:click={conn}>Connect</button>
</div>