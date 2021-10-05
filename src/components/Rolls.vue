<template>
    <div :key="task.id" v-for="roll in rolls"> <!-- loops through data -->
        <h3>{{ roll.result }}</h3>
    </div>
</template>

<script>
export default {
    name: 'Tasks',
    props: {
        rolls: Array
    }
}
</script>