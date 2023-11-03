<script lang="ts">
    import { FlickModel } from "~/models/flicks";

    export let item: FlickModel; 
</script>

<page>
    <gridLayout height="280" borderRadius="10" class="bg-secondary" rows="*, auto, auto" columns="*" margin="5 10" padding="0">
          <image row="0" margin="0" stretch="aspectFill" src="{item.image}" />
          <label row="1" margin="10 10 0 10" fontWeight="700" class="text-primary" fontSize="18" text="{item.title}" />
          <label row="2" margin="0 10 10 10" class="text-secondary" fontSize="14" textWrap="true" text="{item.description}" />
    </gridLayout>
</page>

<style lang="scss">

</style>