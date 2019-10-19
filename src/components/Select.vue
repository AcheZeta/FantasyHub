<template>
  <el-dropdown>
    <el-button type="primary" class="selectInvest" @click="open">
      Invertir
      <i class="el-icon-arrow-down el-icon--right"></i>
    </el-button>
    <el-dropdown-menu slot="dropdown">
      <el-dropdown-item>$25</el-dropdown-item>
      <el-dropdown-item>$50</el-dropdown-item>
      <el-dropdown-item>$100</el-dropdown-item>
    </el-dropdown-menu>
  </el-dropdown>
</template>

<script>
export default {
  methods: {
    open () {
      this.$confirm(
        'Antes de Procesar tu pago confirma la cantidad que seas invertir',
        {
          confirmButtonText: 'OK',
          cancelButtonText: 'Modificar',
          center: true
        }
      )
        .then(() => {
          this.$message({
            type: 'success',
            message: 'ENHORABUENA, tu inversión ha sido registrada'
          })
        })
        .catch(() => {
          this.$message({
            type: 'info',
            message: 'Selecciona la cantidad a invertir'
          })
        })
    }
  }
}
</script>

<style lang="scss" scoped>
@import "~/assets/scss/element-variables.scss";
@import url("https://fonts.googleapis.com/css?family=Nunito&display=swap");

.selectInvest {
  color: #062f4f;
  background-color: #87f96e;
  border-color: #87f96e;
}

.el-dropdown {
  vertical-align: top;
}
.el-dropdown + .el-dropdown {
  margin-left: 15px;
}
.el-icon-arrow-down {
  font-size: 12px;
}
</style>
