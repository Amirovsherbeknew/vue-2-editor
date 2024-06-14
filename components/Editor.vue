<template>
    <div><button @click="getdata">Get url</button>
        <div >
            <vue-document-editor :content.sync="content" />
        </div>
    </div>
</template>

<script>
export default {
    name: 'Editor',
    data() {
        return {
            content: ["<h1>Hello!</h1>Fill this page with text and new pages will be <br><br><br><br><br><br><br><br><br><br> <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>s<br><br><br><br> created as it overflows.<h1>Hello!</h1>Fill this page with text and test case", "asdsad"]
        }
    },
    watch: {
        content() {
            console.log(this.content)
        }
    },
    methods: {
        getdata() {
            const url = 'https://instagram-scraper-api2.p.rapidapi.com/v1.2/reels?username_or_id_or_url=mrbeast';
            const headers = new Headers({
                'x-rapidapi-host': 'instagram-scraper-api2.p.rapidapi.com',
	            'x-rapidapi-key': '7533d54e18msh86206cd27fffb17p1dd9e0jsne4f96fea8dbf'
            });

            fetch(url, {
                method: 'GET', // or 'POST' or any other HTTP method
                headers: headers
            })
                .then(response => {
                    if (!response.ok) {
                        throw new Error('Network response was not ok ' + response.statusText);
                    }
                    return response.json();
                })
                .then(data => {
                    console.log(data); // Handle the JSON data from the response
                })
                .catch(error => {
                    console.error('There has been a problem with your fetch operation:', error);
                });

        }
    }
}
</script>

<style scoped>
/* Component style */
</style>