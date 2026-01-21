---
name: understand-get_interface
description: undertanding the key property of get_interface MCP command
---

JSON 数据当中 _id是接口的ID，method是HTTP请求方法，title 是接口的名称，query_path或者path 是请求路径, req_body_type是请求体的类型，包括raw,form,json

res_body_is_json_schema 表示返回数据是否是JSON Schema类型的表示

req_body_form 是表单类型的请求参数，其中 name是参数名称，type是类型，desc是描述和备注，required表示是否必传

req_params 是请求的路径path上的参数，其中 name是参数名称，type是类型，desc是描述和备注

req_headers 是请求的自定义Header，其中 name是参数名称，type是类型，desc是描述和备注，required表示是否必传

req_query 是请求的URI上的 QueryString 参数，其中 name是参数名称，type是类型，desc是描述和备注

res_body 是返回的数据，res_body_type 是返回的数据格式，包括 json,raw

输出时，应该直接说明 请求方法 请求路径，例如 GET base_path/path，注意一定要加上项目内指定的路径前缀，然后再使用表格列出请求参数，再输出返回数据
