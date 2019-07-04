<template>
  <a-table :columns="columns" :dataSource="data" :rowSelection="rowSelection" 
  bordered
  :pagination="pagination"
  :loading="loading"
  @change="handleTableChange"/>
</template>
<script>
const columns = [{
  title: 'Name',
  dataIndex: 'name',
  key: 'name',
}, {
  title: 'Age',
  dataIndex: 'age',
  key: 'age',
  width: '12%',
}, {
  title: 'Address',
  dataIndex: 'address',
  width: '30%',
  key: 'address',
}];

const pagination = [{

}]

const data = [{
  key: 1,
  name: 'John Brown sr.',
  age: 60,
  address: 'New York No. 1 Lake Park',
  children: [{
    key: 11,
    name: 'John Brown',
    age: 42,
    address: 'New York No. 2 Lake Park',
  }, {
    key: 12,
    name: 'John Brown jr.',
    age: 30,
    address: 'New York No. 3 Lake Park',
    children: [{
      key: 121,
      name: 'Jimmy Brown',
      age: 16,
      address: 'New York No. 3 Lake Park',
    }],
  }, {
    key: 13,
    name: 'Jim Green sr.',
    age: 72,
    address: 'London No. 1 Lake Park',
    children: [{
      key: 131,
      name: 'Jim Green',
      age: 42,
      address: 'London No. 2 Lake Park',
      children: [{
        key: 1311,
        name: 'Jim Green jr.',
        age: 25,
        address: 'London No. 3 Lake Park',
      }, {
        key: 1312,
        name: 'Jimmy Green sr.',
        age: 18,
        address: 'London No. 4 Lake Park',
      }],
    }],
  }],
}, {
  key: 2,
  name: 'Joe Black',
  age: 32,
  address: 'Sidney No. 1 Lake Park',
}];

const rowSelection = {
  // 选中项发生变化时的回调
  onChange: (selectedRowKeys, selectedRows) => {
    console.log('指定选中项的 key 数组selectedRowKeys:',selectedRowKeys,'选中的行数据selectedRows:', selectedRows);
  },
  // 用户手动选择/取消选择某列的回调
  onSelect: (record, selected, selectedRows) => {
    console.log('手动选择/取消某列对应的数据及子集的数据:record',record, '是否选择:selected',selected, '选中的行数据:selectedRows',selectedRows);
  },
  // 用户点击全选/全取消的回调
  onSelectAll: (selected, selectedRows, changeRows) => {
    console.log('是否全选:selected',selected, '选中的行数据:selectedRows',selectedRows, changeRows);
  },
};

export default {
  data() {
    return {
      data,
      columns,
      rowSelection,
      pagination: {},
      loading: false,
    }
  },
  methods: {
    handleTableChange (pagination, filters, sorter) {}
  }
}
</script>