<template>
  <div v-for="(log, logidx) in logs">
    <wei-chun-service :logs="log" :format="'bullet'" />
  </div>
</template>

<script>
import weiChunService from './wei-chun-service.vue';
export default {
  components: {
    weiChunService,
  },
  data() {
    return {
      logs: [
        [
          {
            title: 'SUBMITTED_APPLICATION',
            created_by_name: 'Li',
            action: '',
            description: '',
            data: [
              {
                field: 'COUNTRY',
                value: 'MY',
              },
              {
                field: 'COUNTRY',
                value: 'MY',
              },
            ],
          },
        ],
        [
          [
            {
              title: 'SUBMITTED_APPLICATION',
              created_by_name: 'Li',
              action: '',
              description: '',
              data: [
                {
                  field: 'COUNTRY',
                  value: 'MY',
                },
                {
                  field: 'COUNTRY',
                  value: 'MY',
                },
              ],
            },
          ],
          [
            {
              title: 'SUBMITTED_APPLICATION',
              created_by_name: 'Li',
              action: '',
              description: '',
              data: [
                {
                  field: 'COUNTRY',
                  value: 'MY',
                },
                {
                  field: 'COUNTRY',
                  value: 'MY',
                },
              ],
            },
          ],
        ],
      ],
    };
  },
};
</script>
