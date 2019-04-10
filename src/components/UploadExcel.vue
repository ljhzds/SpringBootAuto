<template>
	<div>
		<p>根据xlsx格式的配置文件，直接生成基于表结构的增删改查的springboot工程代码</p>
		<a id='templateDownload' :href='templateDownUrl'>模板配置文件下载</a>
		<br><br>
		<a id='codeDownload' :href='codeDownUrl' :hidden="downTagHidden">代码下载地址</a>
		<br><br>
		<file-upload :url='url' :accept='accept' :btn-label='btnLabel' :btn-uploading-label='btnUploadingLabel' :thumb-url='thumbUrl'
		 :headers="headers" @change="onFileChange" @success="onSuccess" @error="onError"></file-upload>
	</div>
</template>

<script>
	import Vue from 'vue'
	import FileUpload from 'v-file-upload'
	Vue.use(FileUpload)

	export default {
		name: 'UploadExcel',
		data() {
			return {
				templateDownUrl: 'http://127.0.0.1:5000/download/tables.xlsx',
				downTagHidden: true,
				codeDownUrl: '#',
				url: 'http://127.0.0.1:5000/api/upload',
				headers: {
					// 'access-token': '<your-token>'
				},
				accept: '.xlsx',
				btnLabel: '请选择项目的配置文件，必须是xlsx格式',
				btnUploadingLabel: '正在生成项目代码，请稍候',
				filesUploaded: []
			}
		},
		methods: {
			thumbUrl(file) {
				return null
			},
			onFileChange(file) {
				// Handle files like:
				this.fileUploaded = file
			},
			onSuccess(event) {
				this.downTagHidden = false
				this.codeDownUrl = 'http://127.0.0.1:5000/download/'+event.currentTarget.response.tarfilename
			},
			onError(e) {
				this.error = e
			}
		}
	}
</script>
