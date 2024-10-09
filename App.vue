<template>
  <div class="container">
    <!-- 标题部分 -->
    <div class="header">
      <h1>契約者積立金・互助金単価マスター一覧</h1>
      <div class="date-selection">
        <label for="start-date">年月日</label>
        <select v-model="startDate" id="start-date">
          <option v-for="year in years" :key="year" :value="year">{{ year }}</option>
        </select>
        <span>〜</span>
        <select v-model="endDate" id="end-date">
          <option v-for="year in years" :key="year" :value="year">{{ year }}</option>
        </select>
      </div>
      <div class="user-info">テスト管理者</div>
    </div>

    <!-- 数据表格部分 -->
    <table class="data-table">
      <thead>
        <tr>
          <th>契約区分</th>
          <th>鳥の種類</th>
          <th>契約者積立金単価</th>
          <th>経営支援互助金単価</th>
          <th>焼却・埋却等互助金単価</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(row, index) in tableData" :key="index">
          <td>{{ row.contractType }}</td>
          <td>{{ row.birdType }}</td>
          <td>{{ row.accumulationFee }}</td>
          <td>{{ row.supportFee }}</td>
          <td>{{ row.disposalFee }}</td>
        </tr>
      </tbody>
    </table>

    <!-- 底部按钮部分 -->
    <div class="buttons">
      <button @click="saveData">保存</button>
      <button @click="goBack">戻る</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      startDate: "平成24/04/01",
      endDate: "平成27/03/31",
      years: ["平成24/04/01", "平成25/04/01", "平成26/04/01", "平成27/03/31"],
      tableData: [
        { contractType: "家族型", birdType: "採卵鶏（成鶏）", accumulationFee: 4.5, supportFee: 730, disposalFee: 80 },
        { contractType: "家族型", birdType: "採卵鶏（育成鶏）", accumulationFee: 2.5, supportFee: 330, disposalFee: 80 },
        { contractType: "家族型", birdType: "肉用鶏", accumulationFee: 0.3, supportFee: 20, disposalFee: 80 },
        { contractType: "家族型", birdType: "種鶏（成鶏）", accumulationFee: 6.0, supportFee: 990, disposalFee: 80 },
        { contractType: "家族型", birdType: "種鶏（育成鶏）", accumulationFee: 3.0, supportFee: 460, disposalFee: 80 },
        { contractType: "家族型", birdType: "採卵鶏（成鶏）", accumulationFee: 6.0, supportFee: 870, disposalFee: 80 },
        { contractType: "家族型", birdType: "採卵鶏（育成鶏）", accumulationFee: 3.0, supportFee: 400, disposalFee: 80 },
        { contractType: "企業型", birdType: "肉用鶏", accumulationFee: 0.3, supportFee: 25, disposalFee: 80 },
        { contractType: "企業型", birdType: "種鶏（成鶏）", accumulationFee: 7.5, supportFee: 1,220, disposalFee: 80 },
        { contractType: "企業型", birdType: "種鶏（育成鶏）", accumulationFee: 3.0, supportFee: 560, disposalFee: 80 },
        { contractType: "鶏以外", birdType: "うずら", accumulationFee: 1.5, supportFee: 200, disposalFee: 80 },
        { contractType: "鶏以外", birdType: "あひる", accumulationFee: 1.0, supportFee: 1, disposalFee: 80 },
        { contractType: "鶏以外", birdType: "ぎじ", accumulationFee: 1.0, supportFee: 1, disposalFee: 80 },
        { contractType: "鶏以外", birdType: "ほろほろ鳥", accumulationFee: 1.0, supportFee: 1, disposalFee: 80 },
        { contractType: "鶏以外", birdType: "七面鳥", accumulationFee: 1.0, supportFee: 1, disposalFee: 80 },
        { contractType: "鶏以外", birdType: "だちょう", accumulationFee: 1.0, supportFee: 11, disposalFee: 1 }
      ],
    };
  },
  methods: {
    saveData() {
      // 保存数据的逻辑
      alert("データが保存されました！");
    },
    goBack() {
      // 返回按钮逻辑
      alert("前の画面に戻ります。");
    },
  },
};
</script>

<style scoped>
.container {
  width: 80%;
  margin: 0 auto;
  padding: 20px;
  background-color: #f9f9f9;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.date-selection {
  display: flex;
  align-items: center;
}

.data-table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
}

.data-table th, .data-table td {
  border: 1px solid #ccc;
  padding: 10px;
  text-align: center;
}

.buttons {
  margin-top: 20px;
  display: flex;
  justify-content: flex-end;
}

button {
  margin-left: 10px;
  padding: 10px 20px;
  background-color: #007bff;
  color: white;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}
</style>
