<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Laporan Keuangan</title>
<link rel="stylesheet" href="style.css">
<style>
body { font-family: Arial, sans-serif; background: #f4f4f9; margin: 0; padding: 0; }
header { text-align: center; padding: 20px 10px; }
header h1 { margin: 5px 0; font-size: 1.5em; }
.summary { display: flex; justify-content: center; gap: 10px; margin: 15px 0; flex-wrap: wrap; }
.card { padding: 15px; border-radius: 8px; box-shadow: 0 2px 5px rgba(0,0,0,0.1); text-align: center; min-width: 100px; flex: 1; color: white; font-weight: bold; display: flex; flex-direction: column; align-items: center; justify-content: center; transition: transform 0.3s, background-color 0.5s; }
.card span { margin-top: 5px; font-size: 1.1em; transition: transform 0.3s; }
.income { background: #28a745; }
.expense { background: #dc3545; }
.balance { background: #007bff; }
.container { max-width: 1000px; margin: 20px auto; background: white; padding: 15px; border-radius: 8px; box-shadow: 0 2px 5px rgba(0,0,0,0.1); }
.form-group, .filter-group { display: flex; flex-wrap: wrap; gap: 5px; margin-bottom: 10px; }
input, select, button { padding: 8px; border-radius: 5px; border: 1px solid #ccc; flex: 1 1 120px; }
button { cursor: pointer; }
.btn-add { background: #007bff; color: white; border: none; }
.btn-exp { background: #28a745; color: white; border: none; width: 100%; margin-top: 10px; }
.btn-delete-selected { background: #dc3545; color: white; border: none; margin-bottom:10px; padding:8px 10px; border-radius:5px; display:none; }
.table-container { overflow-x: auto; }
table { width: 100%; border-collapse: collapse; margin-top: 5px; }
table, th, td { border: 1px solid #ddd; }
th { background: #28a745; color: white; padding: 10px; min-width: 50px; }
td { text-align: center; padding: 8px; min-width: 50px; }
.aksi-btn { cursor: pointer; border: none; background: none; font-size: 16px; margin: 0 3px; color:#007bff; }
#chartContainer { margin-top: 20px; height: 30px; display: flex; border-radius: 5px; overflow: hidden; box-shadow: 0 1px 3px rgba(0,0,0,0.2); }
.bar { height: 100%; transition: width 0.8s; }
.incomeBar { background: linear-gradient(90deg,#28a745,#7ef293); }
.expenseBar { background: linear-gradient(90deg,#dc3545,#f78c8c); }
.modal { display:none; position:fixed; z-index:1000; left:0; top:0; width:100%; height:100%; overflow:auto; background: rgba(0,0,0,0.4); }
.modal-content { background:white; margin:10% auto; padding:20px; border-radius:8px; width:90%; max-width:400px; box-shadow:0 2px 5px rgba(0,0,0,0.3); }
.modal-content input, .modal-content select { width:100%; margin-bottom:10px; }
.modal-content button { width:100%; margin-top:5px; }
@media(max-width:600px){
  header h1 { font-size: 1.2em; }
  .form-group, .filter-group { flex-direction: column; }
  input, select, button { flex: 1 1 100%; }
  table, th, td { font-size: 0.9em; }
}
</style>
</head>
<body>

<header>
<h1>Laporan Keuangan</h1>
<div class="summary">
  <div class="card income">💰<strong>Pemasukan</strong><span id="totalIncome">Rp 0</span></div>
  <div class="card expense">🛑<strong>Pengeluaran</strong><span id="totalExpense">Rp 0</span></div>
  <div class="card balance">🏦<strong>Saldo</strong><span id="balance">Rp 0</span></div>
</div>
<div id="chartContainer">
  <div class="bar incomeBar" style="width:50%"></div>
  <div class="bar expenseBar" style="width:50%"></div>
</div>
</header>

<div class="container">
<div class="form-group">
  <input type="date" id="dateInput">
  <input type="text" id="descInput" placeholder="Deskripsi">
  <input type="text" id="amountInput" placeholder="Jumlah">
  <select id="memberSelect" onchange="memberOptionChange()"></select>
  <input type="text" id="sourceInput" placeholder="Sumber Dana">
  <select id="typeInput">
    <option value="pemasukan">Pemasukan</option>
    <option value="pengeluaran">Pengeluaran</option>
  </select>
  <button class="btn-add" onclick="addTransaction()">Tambah Transaksi</button>
</div>

<div class="filter-group">
  <select id="filterMember">
    <option value="all">Semua Anggota</option>
  </select>
  <select id="filterType">
    <option value="all">Semua Tipe</option>
    <option value="pemasukan">Pemasukan</option>
    <option value="pengeluaran">Pengeluaran</option>
  </select>
  <button onclick="applyFilter()">Terapkan Filter</button>
</div>

<button class="btn-delete-selected" id="btnDeleteSelected" onclick="deleteSelected()">Hapus Terpilih</button>

<div class="table-container">
<table>
<thead>
  <tr>
    <th><input type="checkbox" id="selectAll" onchange="toggleSelectAll(this)"></th>
    <th>No</th>
    <th>Tanggal</th>
    <th>Deskripsi</th>
    <th>Anggota</th>
    <th>Sumber Dana</th>
    <th>Pemasukan</th>
    <th>Pengeluaran</th>
    <th>Status</th>
    <th>Aksi</th>
  </tr>
</thead>
<tbody id="transactionTable"></tbody>
</table>
</div>

<button class="btn-exp" onclick="exportExcel()">Export Excel</button>
</div>

<!-- Modal Edit -->
<div id="editModal" class="modal">
  <div class="modal-content">
    <h3>Edit Transaksi</h3>
    <input type="date" id="editDate">
    <input type="text" id="editDesc" placeholder="Deskripsi">
    <input type="text" id="editAmount" placeholder="Jumlah">
    <select id="editMember"></select>
    <input type="text" id="editSource" placeholder="Sumber Dana">
    <select id="editType">
      <option value="pemasukan">Pemasukan</option>
      <option value="pengeluaran">Pengeluaran</option>
    </select>
    <button onclick="saveEdit()">Simpan</button>
    <button onclick="closeModal()">Batal</button>
  </div>
</div>

<!-- Link ke file JavaScript eksternal (potongan 2) -->
<script src="script.js"></script>

</body>
</html>
