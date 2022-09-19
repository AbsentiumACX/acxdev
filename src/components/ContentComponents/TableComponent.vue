<template>
    <div>
        <table width="100%" style="border: 1px solid #eee; border-collapse: collapse;">
            <thead>
                <tr>
                    <th width="80%" scope="col" style="border: 1px solid #eee; border-collapse: collapse;">Vaardigheid</th>
                    <th width="20%" scope="col" style="border: 1px solid #eee; border-collapse: collapse;">Jaren ervaring</th>
                </tr>
            </thead>
            <tbody>
                <template v-for="skill in skills" v-bind:key="skill">
                    <tr>
                        <td style="border: 1px solid #eee; border-collapse: collapse;">{{skill.skill}}</td>
                        <td style="border: 1px solid #eee; border-collapse: collapse;">{{skill.experience}}</td>
                    </tr>
                </template>
            </tbody>
        </table>
    </div>
</template>

<script>
    import axios from 'axios'

    export default {
        name: 'TableComponent',
        data() {
            return {
                skills: null,
            }
        },
        created: function() {
            axios.get('http://localhost:8000/api/skills').then(res=> {
                this.skills = res.data
            })
        }
    }
</script>

<style>

</style>