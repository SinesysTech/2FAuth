<script setup>
    const props = defineProps({
        selectedCount: Number
    })
</script>

<template>
    <div class="toolbar has-text-centered">
        <div class="columns">
            <div class="column has-nowrap px-0">
                <!-- selected label -->
                <span class="has-text-grey mr-1">{{ $t('commons.x_selected', { count: selectedCount }) }}</span>
                <!-- deselect all -->
                <button type="button" id="btnUnselectAll" @click="$emit('clear-selected')" class="clear-selection delete mr-4" :style="{visibility: selectedCount > 0 ? 'visible' : 'hidden'}" :title="$t('commons.clear_selection')"></button>
                <!-- select all button -->
                <button type="button" id="btnSelectAll" @click="$emit('select-all')" class="button mr-5 has-line-height p-1 is-ghost has-text-grey" :title="$t('commons.select_all')">
                    <span>{{ $t('commons.check_all') }}</span>
                    <FontAwesomeIcon class="ml-1" :icon="['fas', 'check-square']" />
                </button>
                <!-- sort asc/desc buttons -->
                <button type="button" id="btnSortAscending" @click="$emit('sort-asc')" class="button has-line-height p-1 is-ghost has-text-grey" :title="$t('commons.sort_ascending')">
                    <FontAwesomeIcon :icon="['fas', 'sort-alpha-down']" />
                </button>
                <button type="button" id="btnSortDescending" @click="$emit('sort-desc')" class="button has-line-height p-1 is-ghost has-text-grey" :title="$t('commons.sort_descending')">
                    <FontAwesomeIcon :icon="['fas', 'sort-alpha-up']" />
                </button>
            </div>
        </div>
    </div>
</template>