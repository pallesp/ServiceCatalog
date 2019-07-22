<template>
    <span>
        <service-search></service-search>
        <service-results></service-results>
    </span>
</template>

<script>
import ServiceResults from '@/components/ServiceResults';
import ServiceSearch from '@/components/ServiceSearch';


export default {
    name: 'home',
    components: {
        ServiceSearch,
        ServiceResults
    }
};
</script>
