<template>
  <div>
    <q-btn color="primary" label="添加一个清单" @click="show = true"/>
    <q-dialog v-model="show">
      <q-card style="min-width: 300px">
        <q-card-section>
          <div class="text-h6">添加一个清单</div>
        </q-card-section>

        <q-separator/>

        <q-card-section style="max-height: 50vh" class="scroll">
          <q-form class="q-gutter-md" ref="form">
            <q-input outlined v-model="form.title" label="输入标题" lazy-rules
                     :rules="[ val => val && val.trim() && val.trim().length > 0 || '标题不能为空噢']"/>
            <q-input outlined v-model="form.desc" autogrow type="textarea" label="描述下这个清单吧"/>
          </q-form>
        </q-card-section>

        <q-separator/>

        <q-card-actions align="right">
          <q-btn label="取消" color="white" text-color="black" v-close-popup/>
          <q-btn label="确定" color="primary" @click="submit"/>
        </q-card-actions>
      </q-card>
    </q-dialog>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  data() {
    return {
      show: false,
      form: {
        title: '',
        desc: '',
      },
    };
  },
  methods: {
    submit() {
      this.$refs.form.validate()
        .then((success) => {
          if (success) {
            console.log('ojbk');
          }
        });
    },
  },
};
</script>

<style scoped>

</style>
