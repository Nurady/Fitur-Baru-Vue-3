<template>
    <Suspense>
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
    </div>
</template>

<script>
import Users from '@/components/Users'
import Posts from '@/components/Posts'
import Modal from '@/components/Modal'

export default{
    components: { Users, Posts, Modal },      
}
</script>

<style>

</style>