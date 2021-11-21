<script lang="ts">
    import { onMount } from "svelte";
    import {ethers} from 'ethers'
    import { initSvelteWeb3 } from '@chiuzon/svelteweb3'

    const fetchLibrary = (provider: any) => {
        const _provider = new ethers.providers.Web3Provider(provider)
        _provider.pollingInterval = 1000
        return _provider
    }
    
    onMount(async () => {
        initSvelteWeb3(fetchLibrary)
    })

</script>

<slot />