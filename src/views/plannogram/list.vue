<template>
    <div>
        <Menu/>
        <div class="container">
            <h1 class="m0">Plannogram</h1>
            <div class="row">
                <div class="col">
                    <p class="mt5 mb20 tc-green">Manage Data Here</p>
                </div>
                <div class="col flex">
                    <router-link to="/add-plannogram">
                        <button class="bt-green">Add Plannogram</button>
                    </router-link>
                </div>
            </div>
            <div class="row bg-blue mt10 p10">
                <div class="col">
                    <input
                        class="search-field"
                        type="text"
                        id="deskripsi"
                        placeholder="Tambah deskripsi..."
                    />
                </div>
                <div class="col flex">
                    <button class="bt-blue">Filter</button>
                </div>
            </div>
            <div class="mt50">
                <table>
                    <thead>
                        <tr>
                            <th>PLANNOGRAM NAME</th>
                            <th>BACKGROUND NAME</th>
                            <th>BROADCAST SCHEDULE</th>
                            <th>VALID FROM</th>
                            <th>VALID UNTIL</th>
                            <th>PLANNOGRAM STATUS</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="item of list_plannogram" :key="item.id">
                            <td class="center">{{ item.name }}</td>
                            <td class="center">
                                <img :src="item.background" alt="Background Image" class="background-image"/>
                            </td>
                            <td class="center">{{ item.schedule }}</td>
                            <td class="center"><label class="label-green">{{ item.validForm }}</label></td>
                            <td class="center"><label class="label-green">{{ item.validUntil }}</label></td>
                            <td class="center">
                                <div v-if="item.status === 1">
                                    <label class="label-green">Active</label>
                                </div>
                                <div v-if="item.status === 2">
                                    <label class="label-blue">Inactive</label>
                                </div>

                            </td>
                            <td class="center">
                                <div class="mt5">
                                    <router-link to="/edit-plannogram">
                                        <img src="../../assets/icons/edit.svg">
                                    </router-link>
                                </div>
                                <div class="mt5">
                                    <router-link to="/detail-plannogram">
                                        <img src="../../assets/icons/detail.svg">
                                    </router-link>
                                </div>
                                <div class="mt5">
                                    <img src="../../assets/icons/delete.svg">
                                </div>
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</template>

<script>
import Menu from "../../components/menu.vue"

export default {
	name: 'list-plannogram',
	components: {
		Menu
	},
    data(){
        return {
            list_plannogram: [
                {
                    id: "1",
                    name: "Flash Sale Minggu Ini",
                    background: require('@/assets/images/flashsale.png'),
                    schedule: "senin",
                    validForm: "17-11-2023",
                    validUntil: "23-11-2023",
                    status: 1
                },
                {
                    id: "2",
                    name: "Produk Terbaru",
                    background: require('@/assets/images/produkbaru.png'),
                    schedule: "kamis",
                    validForm: "17-11-2023",
                    validUntil: "18-11-2023",
                    status: 2
                },
                {
                    id: "3",
                    name: "Diskon 50%",
                    background: require('@/assets/images/diskon.png'),
                    schedule: "minggu",
                    validForm: "28-09-2023",
                    validUntil: "28-12-2023",
                    status: 1
                },
            ]
        }
    }
}
</script>
<style scoped>
.background-image{
    width: 100px;
    height: auto;
}
</style>