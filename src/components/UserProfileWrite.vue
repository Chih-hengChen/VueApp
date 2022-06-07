<template>
    <div class="card edit-field">
        <div class="card-body">
            <label for="edit-posts" class="form-label"></label>
            <textarea v-model="content" class="form-control" id="edit-posts" rows="3" placeholder="有什么新鲜事想分享给大家？"></textarea>
            <button @click="post_a_post" type="button" class="btn btn-primary btn-sm">发送</button>
        </div>
    </div>
    
</template>

<script>
import { ref } from 'vue';
import $ from 'jquery';
import { useStore } from 'vuex';

export default {
  name: 'UserProfileWrite',
  setup(props, context) {
      const store = useStore();

      let content = ref('');

      const post_a_post = () => {
          $.ajax({
              url: "https://app165.acapp.acwing.com.cn/myspace/post/",
              type: "POST",
              data: {
                  content: content.value,
              },
              headers: {
                  'Authorization': "Bearer " + store.state.user.access,
              },
              success(resp) {
                  if (resp.result === "success") {
                      if (content.value !== "") {
                        context.emit('post_a_post', content.value);
                        content.value = "";
                      }    
                  }
              }
          });
      }

      return {
          content,
          post_a_post,
      }
  }
};
</script>

<style scoped>
button {
    margin-top: 10px;
}
.edit-field{
    margin-top: 10px;
}
</style>