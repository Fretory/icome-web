<template>
  <el-card style="margin-bottom:20px;">
    <div slot="header" class="clearfix">
      <span>About me</span>
    </div>

    <div class="user-profile">
      <div class="box-center">
        <!--        <pan-thumb :image="user.avatar" :height="'100px'" :width="'100px'" :hoverable="false">-->
        <!--          <div>Hello</div>-->
        <!--          {{ user.name }}-->
        <!--        </pan-thumb>-->
        <el-avatar :size="125" :src="computeAvatar(user.name)" />
      </div>
      <div class="box-center">
        <div class="user-name text-center">{{ user.name }}</div>
        <!--        <div class="user-role text-center text-muted">{{ user.role }}</div>-->
      </div>
    </div>

    <div class="user-bio">
      <div class="user-education user-bio-section">
        <div class="user-bio-section-header"><svg-icon icon-class="education" /><span>Education</span></div>
        <div class="user-bio-section-body">
          <div class="text-muted">
            Hubei University of Technology
          </div>
        </div>
      </div>
    </div>

    <div class="user-bio">
      <div class="user-education user-bio-section">
        <div class="user-bio-section-header"><i class="el-icon-date" /><span>Birthday</span></div>
        <div class="user-bio-section-body">
          <div class="text-muted">
            {{ user.birthday }}
          </div>
        </div>
      </div>
    </div>

    <div class="user-bio">
      <div class="user-education user-bio-section">
        <div class="user-bio-section-header"><i class="el-icon-user" /><span>Sex</span></div>
        <div class="user-bio-section-body">
          <div class="text-muted">
            {{ user.sex }}
          </div>
        </div>
      </div>
    </div>

    <div class="user-bio">
      <div class="user-education user-bio-section">
        <div class="user-bio-section-header"><i class="el-icon-phone" /><span>Tel</span></div>
        <div class="user-bio-section-body">
          <div class="text-muted">
            {{ user.telephone }}
          </div>
        </div>
      </div>
    </div>
  </el-card>
</template>

<script>
// import PanThumb from '@/components/PanThumb'
import { generateFromString } from 'generate-avatar'

export default {
  // components: { PnThumb },
  props: {
    user: {
      type: Object,
      default: () => {
        return {
          name: '',
          telephone: '',
          avatar: '',
          role: '',
          sex: '',
          birthday: ''
        }
      }
    }
  },
  methods: {
    generateFromString,
    computeAvatar(username) {
      return `data:image/svg+xml;utf8,${generateFromString(username)}`
    }
  }
}
</script>

<style lang="scss" scoped>
.box-center {
  margin: 0 auto;
  display: table;
}

.text-muted {
  color: #777;
}

.user-profile {
  .user-name {
    font-weight: bold;
  }

  .box-center {
    padding-top: 10px;
  }

  .user-role {
    padding-top: 10px;
    font-weight: 400;
    font-size: 14px;
  }

  .box-social {
    padding-top: 30px;

    .el-table {
      border-top: 1px solid #dfe6ec;
    }
  }

  .user-follow {
    padding-top: 20px;
  }
}

.user-bio {
  margin-top: 20px;
  color: #606266;

  span {
    padding-left: 4px;
  }

  .user-bio-section {
    font-size: 14px;
    padding: 15px 0;

    .user-bio-section-header {
      border-bottom: 1px solid #dfe6ec;
      padding-bottom: 10px;
      margin-bottom: 10px;
      font-weight: bold;
    }
  }
}
</style>
