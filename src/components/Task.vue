<template>
    <div class="task" :class="stateClass">
        <p>{{ task.name }}</p>
    </div>
</template>

<script>
export default {
    props: {
        task: { type: Object, required: true }
    },
    computed: {
        stateClass() {
            return {
                pending: this.task.pending,
                done: !this.task.pending
            }
        }
    }
}
</script>

<style>
    .task  {
        box-sizing: border-box;
        width: 350px;
        height: 150px;
        padding: 10px;
        border-radius: 8px;
        font-size: 2rem;
        font-weight: 300;
        cursor: pointer;
        user-select: none;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .pending {
        border-left: 12px solid #b73229;
        background-color: rgb(209, 21, 21);
    }

    .done {
        border-left: 12px solid #2a9121;
        background-color: rgb(7, 133, 7);
        text-decoration: line-through;
    }

</style> 