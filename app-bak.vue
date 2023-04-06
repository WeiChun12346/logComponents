<template>
  <wei-chun-service :logs="logs3" :format="'bullet'" />
</template>

<script>
import weiChunService from './wei-chun-service.vue';
export default {
  components: {
    weiChunService,
  },
  data() {
    return {
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
              field: '',
              // value: {} | [] | "",
              value: [
                'COUNTRY',
                'CHANGED_FROM',
                '"application need to update the country"',
                'TO',
                '"country updated, thanks"',
              ],
            },
            {
              field: '',
              // value: {} | [] | "",
              value: [
                'COUNTRY',
                'CHANGED_FROM',
                '<b>CHAT</b>',
                'TO',
                '<b>MY</b>',
              ],
            },
            {
              field: '',
              // value: {} | [] | "",
              value: [
                'COUNTRY',
                'CHANGED_FROM',
                '<u>CHAT</u>',
                'TO',
                '<u>MY</u>',
              ],
            },
            {
              field: 'SUBMITTED_APPLICATION',
              // value: {} | [] | "",
              value: ['reason 1', 'reason 2', 'reason 3'].toString(),
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
      logs3: [
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
    };
  },
};
</script>
