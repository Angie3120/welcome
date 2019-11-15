---
title: "Transaction"
excerpt: ""
---
# group `transactioncppapi` 

Type-safe C++ wrappers for transaction C API.

There are some methods from the [Transaction C API](#group__transactioncapi) that can be used directly from C++

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline action `[`get_action`](#get_action)`(uint32_t type,uint32_t index)`            | Retrieve the indicated action from the active transaction. 
`public inline void `[`check_auth`](#check_auth)`(const bytes & trx_packed,const vector< permission_level > & permissions)`            | 
`public inline void `[`check_auth`](#check_auth)`(const char * serialized_transaction,size_t size,const vector< permission_level > & permissions)`            | 
`public inline void `[`check_auth`](#check_auth)`(const transaction & trx,const vector< permission_level > & permissions)`            | 
`class `[`eosio::transaction_header`](#transaction_header) | 
`class `[`eosio::transaction`](#transaction) | 
`class `[`eosio::deferred_transaction`](#deferred_transaction) | 

## Members

#### `public inline action `[`get_action`](#group__transactioncppapi_1gac01a00482f2dc95bf4850b2e8213ee90)`(uint32_t type,uint32_t index)` 

Retrieve the indicated action from the active transaction. 
#### Parameters
* `type` - 0 for context free action, 1 for action 

* `index` - the index of the requested action 

#### Returns
the indicated action

#### `public inline void `[`check_auth`](#group__transactioncppapi_1gaae55081c4b4068a5cb2a7dae2b4a051a)`(const bytes & trx_packed,const vector< permission_level > & permissions)` 

#### `public inline void `[`check_auth`](#group__transactioncppapi_1ga33cd826341c39c6999ecfe6457bd9dd1)`(const char * serialized_transaction,size_t size,const vector< permission_level > & permissions)` 

#### `public inline void `[`check_auth`](#group__transactioncppapi_1ga422af7cc0363c5993e4eb9a26034b399)`(const transaction & trx,const vector< permission_level > & permissions)` 

# class `eosio::transaction_header` 

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`time`](#group__types_1ga44479e2657d126b44ca53d30c3e670d8)` `[`expiration`](#classeosio_1_1transaction__header_1a2d01d4d651eaab53ef0796bf138ed691) | 
`public `[`region_id`](#group__types_1ga9ff8565896a4a57d1ff8c7c4533a451a)` `[`region`](#classeosio_1_1transaction__header_1a3f03fd4c381e7307f3709d861320e6ff) | 
`public uint16_t `[`ref_block_num`](docs/ transactioncppapi#classeosio_1_1transaction__header_1a7bd1f446f3a9a212183787d223d89766) | 
`public uint32_t `[`ref_block_prefix`](docs/ transactioncppapi#classeosio_1_1transaction__header_1aed4b528cd8a73ac9fa9cb5b7c429f90c) | 
`public `[`unsigned_int`](#structunsigned__int)` `[`net_usage_words`](#classeosio_1_1transaction__header_1a0d66dd30a2c0660eda03dd89cc7c5041) | 
`public `[`unsigned_int`](#structunsigned__int)` `[`kcpu_usage`](#classeosio_1_1transaction__header_1aeece6ee784f4fee73988cbccd017ca57) | number of 8 byte words this transaction can serialize into after compressions
`public `[`unsigned_int`](#structunsigned__int)` `[`delay_sec`](#classeosio_1_1transaction__header_1adbe5ee5f38a82db68162188c49d62f39) | number of CPU usage units to bill transaction for
`public inline  `[`transaction_header`](#classeosio_1_1transaction__header_1a1c08cb91411909dbd0baf0ad83b2b74c)`(`[`time`](#group__types_1ga44479e2657d126b44ca53d30c3e670d8)` exp,`[`region_id`](#group__types_1ga9ff8565896a4a57d1ff8c7c4533a451a)` r)` | 

## Members

#### `public `[`time`](#group__types_1ga44479e2657d126b44ca53d30c3e670d8)` `[`expiration`](#classeosio_1_1transaction__header_1a2d01d4d651eaab53ef0796bf138ed691) 

#### `public `[`region_id`](#group__types_1ga9ff8565896a4a57d1ff8c7c4533a451a)` `[`region`](#classeosio_1_1transaction__header_1a3f03fd4c381e7307f3709d861320e6ff) 

#### `public uint16_t `[`ref_block_num`](docs/ transactioncppapi#classeosio_1_1transaction__header_1a7bd1f446f3a9a212183787d223d89766) 

#### `public uint32_t `[`ref_block_prefix`](docs/ transactioncppapi#classeosio_1_1transaction__header_1aed4b528cd8a73ac9fa9cb5b7c429f90c) 

#### `public `[`unsigned_int`](#structunsigned__int)` `[`net_usage_words`](#classeosio_1_1transaction__header_1a0d66dd30a2c0660eda03dd89cc7c5041) 

#### `public `[`unsigned_int`](#structunsigned__int)` `[`kcpu_usage`](#classeosio_1_1transaction__header_1aeece6ee784f4fee73988cbccd017ca57) 

number of 8 byte words this transaction can serialize into after compressions

#### `public `[`unsigned_int`](#structunsigned__int)` `[`delay_sec`](#classeosio_1_1transaction__header_1adbe5ee5f38a82db68162188c49d62f39) 

number of CPU usage units to bill transaction for

#### `public inline  `[`transaction_header`](#classeosio_1_1transaction__header_1a1c08cb91411909dbd0baf0ad83b2b74c)`(`[`time`](#group__types_1ga44479e2657d126b44ca53d30c3e670d8)` exp,`[`region_id`](#group__types_1ga9ff8565896a4a57d1ff8c7c4533a451a)` r)` 

# class `eosio::transaction` 

```
class eosio::transaction
  : public eosio::transaction_header
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public vector< `[`action`](#structeosio_1_1action)` > `[`context_free_actions`](#classeosio_1_1transaction_1a63d96348ba55ff45b0a5e10ff10a99b6) | 
`public vector< `[`action`](#structeosio_1_1action)` > `[`actions`](#classeosio_1_1transaction_1a02467261e48f0c8a5eb5f59cbdc179ea) | 
`public inline  `[`transaction`](#classeosio_1_1transaction_1a02931fb7d09e29b72434e3917db41f6e)`(`[`time`](#group__types_1ga44479e2657d126b44ca53d30c3e670d8)` exp,`[`region_id`](#group__types_1ga9ff8565896a4a57d1ff8c7c4533a451a)` r)` | 
`public inline void `[`send`](#classeosio_1_1transaction_1a720c4a0394973cde33d608c239d58455)`(uint64_t sender_id,`[`account_name`](#group__types_1ga3b44deb4b3b8d6ebab339d1263692117)` payer) const` | 

## Members

#### `public vector< `[`action`](#structeosio_1_1action)` > `[`context_free_actions`](#classeosio_1_1transaction_1a63d96348ba55ff45b0a5e10ff10a99b6) 

#### `public vector< `[`action`](#structeosio_1_1action)` > `[`actions`](#classeosio_1_1transaction_1a02467261e48f0c8a5eb5f59cbdc179ea) 

#### `public inline  `[`transaction`](#classeosio_1_1transaction_1a02931fb7d09e29b72434e3917db41f6e)`(`[`time`](#group__types_1ga44479e2657d126b44ca53d30c3e670d8)` exp,`[`region_id`](#group__types_1ga9ff8565896a4a57d1ff8c7c4533a451a)` r)` 

#### `public inline void `[`send`](#classeosio_1_1transaction_1a720c4a0394973cde33d608c239d58455)`(uint64_t sender_id,`[`account_name`](#group__types_1ga3b44deb4b3b8d6ebab339d1263692117)` payer) const` 

# class `eosio::deferred_transaction` 

```
class eosio::deferred_transaction
  : public eosio::transaction
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public uint128_t `[`sender_id`](docs/ transactioncppapi#classeosio_1_1deferred__transaction_1af186b02b4546093ed88592aef085b0e4) | 
`public `[`account_name`](#group__types_1ga3b44deb4b3b8d6ebab339d1263692117)` `[`sender`](#classeosio_1_1deferred__transaction_1a82441339af3291e5425b338098d2f896) | 
`public `[`account_name`](#group__types_1ga3b44deb4b3b8d6ebab339d1263692117)` `[`payer`](#classeosio_1_1deferred__transaction_1ab9a8613f83abbdbd9e1101d56fa66a20) | 
`public `[`time`](#group__types_1ga44479e2657d126b44ca53d30c3e670d8)` `[`execute_after`](#classeosio_1_1deferred__transaction_1a2f80b200b62fa63e8ce8cd68f7683d98) | 

## Members

#### `public uint128_t `[`sender_id`](docs/ transactioncppapi#classeosio_1_1deferred__transaction_1af186b02b4546093ed88592aef085b0e4) 

#### `public `[`account_name`](#group__types_1ga3b44deb4b3b8d6ebab339d1263692117)` `[`sender`](#classeosio_1_1deferred__transaction_1a82441339af3291e5425b338098d2f896) 

#### `public `[`account_name`](#group__types_1ga3b44deb4b3b8d6ebab339d1263692117)` `[`payer`](#classeosio_1_1deferred__transaction_1ab9a8613f83abbdbd9e1101d56fa66a20) 

#### `public `[`time`](#group__types_1ga44479e2657d126b44ca53d30c3e670d8)` `[`execute_after`](#classeosio_1_1deferred__transaction_1a2f80b200b62fa63e8ce8cd68f7683d98)