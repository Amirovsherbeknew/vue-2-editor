<template>
    <div>asdkaslk;ldkas
        <div style="width: 600px;height: 400px;padding: 10px; background-color: red;">
            <vue-document-editor :content.sync="content" />
        </div>
    </div>
</template>

<script>
export default {
    name: 'Editor',
    data() {
        return {
            content: ["<h1>Hello!</h1>Fill this page with text and new pages will be created as it overflows.","asdsad"]
        }
    },
    watch: {
        content () {
            console.log(this.content)
        }
    }
}
</script>

<style scoped>
/* Component style */
</style>