<template>
  <q-page class="flex flex-center">
    <mavon-editor v-model="content" ref="md" @imgAdd="imgAdd" @change="change" style="min-height: 780px"/>
  </q-page>
</template>

<script>
import 'mavon-editor/dist/css/index.css'
export default {
  name: 'Letter',
  data () {
    return {
      tab: 'letter',
      splitterModel: 20,
      content: '', // 输入的markdown
      html: '' // 及时转的html
    }
  },
  methods: {
    // 将图片上传到服务器，返回地址替换到md中
    imgAdd (pos, $file) {
      let formdata = new FormData()
      console.log(formdata)
    },
    // 所有操作都会被解析重新渲染
    change (value, render) {
      // render 为 markdown 解析后的结果[html]
      this.html = render
    },
    // 提交
    submit () {
      console.log(this.content)
      console.log(this.html)
    }
  },
  mounted () {

  }
}
</script>
