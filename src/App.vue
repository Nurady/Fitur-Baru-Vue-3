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
</template>

<script>
import Users from '@/components/Users'
import Posts from '@/components/Posts'

export default{
    components: { Users, Posts },      
}
</script>

<style>

</style>