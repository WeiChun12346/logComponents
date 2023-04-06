<template>
  <div>
    <logging
      style="
        border: 1px solid lightgrey;
        padding: 50px;
        margin: 20px;
        font-family: monospace;
        color: grey;
      "
      v-for="(log, idx) in logs"
      :key="idx"
    >
      <template #title>{{ t(log.title) }}</template>
      <template #data v-if="format == 'bullet'">
        <ul v-for="(detail, index) in log.data" :key="index">
          <li v-if="Array.isArray(detail.value)">
            <span v-for="(item, itemIdx) in detail.value">
              <!-- <span>{{ t(item) + ' ' }}</span> -->
              <span v-html="t(item)"></span>&nbsp
            </span>
          </li>
          <li v-else>
            {{ t(detail.field) }} {{ detail.field && detail.value ? ':' : '' }}
            <span v-html="detail.value" />
          </li>
        </ul>
      </template>
      <template #data v-if="format == 'dash'">
        <div v-for="(detail, index) in log.data" :key="index">
          - {{ t(detail.field) }}
          <span v-html="detail.value" />
        </div>
      </template>
    </logging>
  </div>
</template>

<script>
import logging from './logging.vue';
export default {
  props: {
    logs: {
      type: Array,
      default: () => {
        return [];
      },
    },
    format: {
      type: String,
      default: () => {
        return 'bullet';
      },
    },
  },
  components: {
    logging,
  },
  data() {
    return {
      translationEn: {
        CREATED_DRAFT_APPLICATION: 'Create Draft Application',
        DELETED_DRAFT_APPLICATION: 'Deleted Draft Application',
        SAVE_DRAFT_APPLICATION: 'Save Draft Application',
        SUBMITTED_APPLICATION: 'Submitted Application',
        NOTIFICATION_EMAIL_SENT_TO_OWNER: 'Notification email sent to owner',
        RESUBMIT_APPLICATION: 'Resubmit Application',
        STATUS: 'Status',
        DRAFT: 'Draft',
        DELETED: 'Deleted',
        SUBMITTED: 'Submitted',
        PICK_UP_APPLICATION: 'Pick Up Application',
        WAREHOUSE_STATUS_REGISTERED: 'Status : REGISTERED',
        WAREHOUSE_STATUS_RECEIVED: 'Status : RECEIVED',
        RECEIVED_APPLICATION: 'Received Application',
        WAREHOUSE_APPROVAL_NO: 'Warehouse Approval No :',
        WAREHOUSE_APPROVAL_DATE: 'Warehouse Approval Date',
        ACKNOWLEDGEMENT: 'Acknowledgement',
        WAREHOUSE_INVALID: 'Status : Invalid',
        CHANGED_FROM: 'Changed From',
        TO: 'To',
        COUNTRY: 'Guo Jia',
      },
      translationChi: {
        CREATED_DRAFT_APPLICATION: '创建 Draft Application',
        DELETED_DRAFT_APPLICATION: '删除 Draft Application',
        SAVE_DRAFT_APPLICATION: '储存 Draft Application',
        SUBMITTED_APPLICATION: '提交 Application',
        RESUBMIT_APPLICATION: '重新提交 Application',
        NOTIFICATION_EMAIL_SENT_TO_OWNER: '通知邮件已发送给用户',
        STATUS: '状况',
        DRAFT: '草稿',
        DRAFT: '删除',
        SUBMITTED: '提交',
        PICK_UP_APPLICATION: 'Pick Up Application',
        WAREHOUSE_STATUS_REGISTERED: 'Status : REGISTERED',
        WAREHOUSE_STATUS_RECEIVED: 'Status : RECEIVED',
        RECEIVED_APPLICATION: 'Received Application',
        WAREHOUSE_APPROVAL_NO: 'Warehouse Approval No :',
        WAREHOUSE_APPROVAL_DATE: 'Warehouse Approval Date',
        ACKNOWLEDGEMENT: 'Acknowledgement',
        WAREHOUSE_INVALID: 'Status : Invalid',
        CHANGED_FROM: 'Huan',
        TO: 'Qu',
        COUNTRY: 'Guo Jia',
      },
      logs1: [
        {
          title: 'CREATED_DRAFT_APPLICATION',
          created_by_name: 'Li',
          action: '',
          description: '',
          data: [],
        },
        {
          title: 'DELETED_DRAFT_APPLICATION',
          created_by_name: 'Li',
          action: '',
          description: '',
          data: [
            {
              field: 'STATUS',
              value: 'DELETED',
            },
          ],
        },
        {
          title: 'SAVE_DRAFT_APPLICATION',
          created_by_name: 'Li',
          action: '',
          description: '',
          data: [
            {
              field: 'STATUS',
              value: 'DRAFT',
            },
          ],
        },
        {
          title: '',
          created_by_name: 'Li',
          action: '',
          description: '',
          data: [
            {
              field: 'SUBMITTED_APPLICATION',
            },
            {
              field: 'STATUS',
              value: 'SUBMITTED',
            },
            {
              field: 'NOTIFICATION_EMAIL_SENT_TO_OWNER',
            },
          ],
        },
        {
          title: 'RESUBMIT_APPLICATION',
          created_by_name: 'Li',
          action: '',
          description: '',
          data: [
            {
              field: 'SUBMITTED_APPLICATION',
              value: 'Country changed from MY to SG',
            },
          ],
        },
        {
          title: 'PICK_UP_APPLICATION',
          created_by_name: 'Li',
          action: '',
          description: '',
          data: [],
        },
      ],
      logs2: [
        {
          title: 'RECEIVED_APPLICATION',
          created_by_name: 'Li',
          action: '',
          description: '',
          data: [
            {
              field: 'Party Code',
              value: 'DTH',
            },
            {
              field: 'Message Type',
              value: 'JYNASUB',
            },
            {
              field: 'Batch Identification',
              value: 'DTH-JYN-AIR-20230404-10000',
            },
            {
              field: 'Supporting Document',
              value: `<a target="_blank" href="https://play-lh.googleusercontent.com/1-hPxafOxdYpYZEOKzNIkSP43HXCNftVJVttoo4ucl7rsMASXW3Xr6GlXURCubE1tA=w3840-h2160-rw">sample.pdf</a>`,
            },
          ],
        },
        {
          title: 'WAREHOUSE_STATUS_RECEIVED',
          created_by_name: 'Li',
          action: '',
          description: '',
          data: [],
        },
        {
          title: 'WAREHOUSE_STATUS_REGISTERED',
          created_by_name: 'Li',
          action: '',
          description: '',
          data: [
            {
              field: 'WAREHOUSE_APPROVAL_NO',
              value: 'WH-APV-0001',
            },
            {
              field: 'WAREHOUSE_APPROVAL_DATE',
              value: '20230404 12:00',
            },
          ],
        },
        {
          title: 'ACKNOWLEDGEMENT',
          created_by_name: 'Li',
          action: '',
          description: '',
          data: [
            {
              field: 'Party Code',
              value: 'DTH',
            },
            {
              field: 'Message Type',
              value: 'JYNASUB',
            },
            {
              field: 'Batch Identification',
              value: 'DTH-JYN-AIR-20230404-10000',
            },
            {
              field: 'Supporting Document',
              value: `<a target="_blank" href="https://play-lh.googleusercontent.com/1-hPxafOxdYpYZEOKzNIkSP43HXCNftVJVttoo4ucl7rsMASXW3Xr6GlXURCubE1tA=w3840-h2160-rw">sample.pdf</a>`,
            },
          ],
        },
        {
          title: 'WAREHOUSE_INVALID',
          created_by_name: 'Li',
          action: '',
          description: '',
          data: [
            {
              field: 'WAREHOUSE_APPROVAL_NO',
              value: '001 | Invalid City',
            },
            {
              field: 'WAREHOUSE_APPROVAL_DATE',
              value: '001 | Invalid City',
            },
          ],
        },
      ],
    };
  },
  methods: {
    t(value) {
      return this.translationEn[value] ? this.translationEn[value] : value;
    },
  },
};
</script>
