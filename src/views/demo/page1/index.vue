<template>
  <d2-container>
    <template slot="header">Page 1 header</template>
    <el-drawer
    title="我是标题"
    @click.self="handlePanelClick"
    :visible.sync="drawer"
    :direction="direction"
    :before-close="handleClose">
    <span>我来啦!</span>
    </el-drawer>
  </d2-container>
</template>

<script>
import hotkeys from 'hotkeys-js'
export default {
  data () {
    return {
      drawer: false,
      direction: 'rtl'
    }
  },
  mounted () {
    // 绑定搜索功能快捷键 [ 打开 ]
    hotkeys('a', event => {
      event.preventDefault()
      this.drawer = true
    })
  },
  methods: {
    handlePanelClick () {
      alert('hello world')
    },
    handleClose (done) {
      done()
    }
  }
}
</script>
