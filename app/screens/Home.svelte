<script lang="ts">
    import { ItemEventData } from '@nativescript/core';
    import { navigate } from 'svelte-native'
    import { Template } from 'svelte-native/components'
    import Card from '~/components/Card.svelte';
    import Details from '~/screens/Details.svelte';
    import { FlickService } from "~/services/flickService";

    let flicks = FlickService.getInstance().getFlicks();

    const onFlickTap = (event: ItemEventData) => {
        navigate({
        page: Details,
            props: { flickId: flicks[event.index].id }
        })
    }
</script>

<page>
    <actionBar title="NativeFlix" />
    <stackLayout height="100%">
        <listView on:itemTap="{onFlickTap}" height="100%" separatorColor="transparent" items="{flicks}">
            <Template let:item>
                <Card item={item} />
            </Template>
        </listView>
    </stackLayout>
</page>