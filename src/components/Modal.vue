<template>
    <button @click="modalOpen = true">
        Show Modal
    </button>
    <div v-if="modalOpen" class="modal-overlay">
        <div class="modal">
            <div class="modal-header">
                this is header
            </div>
            <div class="modal-body">
                Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dignissimos, tempore nihil omnis neque dolores voluptatum totam sunt, porro aspernatur est quis provident eum nisi eius rem cumque commodi perferendis amet?
            </div>
            <div class="modal-footer">
                <button @click="modalOpen = false">Close</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            modalOpen:false,

        }
    }
}
</script>

<style>
    .modal-overlay {
       position: absolute;
       top: 0;
       bottom: 0;
       left: 0;
       right: 0;
       background: rgba(0, 0, 0, 0.5);
       content: "";
    }

    .modal {
        border: 1px solid #eee;
        background: white;
        position: fixed;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }

    .modal-header {
        border-bottom: 1px solid #eee
    }

    .modal-footer {
        border-top: 1px solid #eee
    }

    .modal-body, .modal-header, .modal-footer {
        padding: 10px
    }
</style>