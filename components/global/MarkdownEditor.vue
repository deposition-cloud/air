<template>
  <div id="top">
    <!-- Text Editor -->
    <TuiEditor
      mode="markdown"
      preview-style="vertical"
      v-model="file"
      @blur="$emit('endEdit')"
    />

    <!-- Markdown Viewer -->
    <!-- <TuiEditorViewer/> -->
  </div>
</template>

<script>
export default {
  props: {
    value: String,
    isEditing: Boolean
  },
  data () {
    return {
      file: '',
      isInComposition: false
    }
  },
  watch: {
    value () {
      this.file = this.value
    },
    file () {
      this.$emit('input', this.file)
    }
  }
}
</script>
