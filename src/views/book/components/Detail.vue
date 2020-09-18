<template>
    <el-fom ref="postForm" :model="postForm">
        <sticky :class-name="'sub-navbar'">
            <el-button v-if="!isEdit" @click="showGuide">显示帮助</el-button>
            <el-button
            v-loading="loading"
            @click="submitForm"
            type="success"
            style="marign-left: 10px"
            >{{ isEdit ? '编辑电子书' : '新增电子书' }}</el-button>
        </sticky>
        <div class="detail-container">
            <el-row>
                <Warning />
                <el-col :span="24">

                </el-col>
                <el-col :span="24">

                </el-col>
            </el-row>
        </div>
    </el-fom>
</template>

<script>
import Sticky from '../../../components/Sticky/index'
import Warning from './Warning.vue'
import { constants } from 'zlib';
export default {
    components: { Sticky, Warning },
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
    .detail-container {
        padding: 40px 50px 20px;
    }
</style>