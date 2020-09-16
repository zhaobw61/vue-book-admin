<template>
    <el-fom ref="postForm" :model="postForm">
        <sticky :class-name="'sub-navbar' + postForm.status">
            <el-button v-if="!isEdit" @click="showGuide">显示帮助</el-button>
            <el-button
            v-loading="loading"
            @click="submitForm"
            type="success"
            style="marign-left: 10px"
            >{{ isEdit ? '编辑电子书' : '新增电子书' }}</el-button>
        </sticky>
    </el-fom>
</template>

<script>
import Sticky from '../../../components/Sticky/index'
import { constants } from 'zlib';
export default {
    components: { Sticky },
    props: {
        isEdit: Boolean
    },
    data() {
        return {
            loading: false,
            postForm: {
                status: 'draft'
            }
        }
    },
    methods: {
        submitForm() {
            this.loading = true;
        },
        showGuide() {
            console.log('show asdasd');
        }
    }
}
</script>

<style lang="scss" scoped>

</style>