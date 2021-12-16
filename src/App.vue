<template>
    <!-- <Suspense>
        <template #default>
            <div>
                <Users />
                    <hr>
                <Posts />
            </div>
        </template>
        <template #fallback>
            <div>Loading . . .</div>
        </template>
    </Suspense>  
    <hr>
    <div>
        <teleport to="#modal">
            <Modal />
        </teleport>
    </div> -->
    <div v-for="user in users" :key="user.id">
        <div>{{ user.name }}</div>
    </div>
</template>

<script>
import axios from 'axios'
import { onMounted, reactive, toRefs } from 'vue'
// import Users from '@/components/Users'
// import Posts from '@/components/Posts'
// import Modal from '@/components/Modal'

export default {
    // components: { Users, Posts, Modal },   
    setup () {
        // const users = ref(null)
        const state = reactive({
            users: []
        })

        const getUsers = async () => {
            let {data} = await axios.get('https://jsonplaceholder.typicode.com/users')
            state.users = data
        }

        onMounted(() => {
            getUsers()
        }) 

        return {
            // state
            ...toRefs(state)
            // users
        }
    }
}
</script>

<style>

</style>