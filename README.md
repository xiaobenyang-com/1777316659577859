# 警察数据查询服务 

一个提供英国警察数据查询的MCP服务器，包括犯罪记录、警察部队、社区信息和拦截搜查数据。
An MCP server providing data queries for the UK police, including criminal records, police forces, community information and interception search data.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| get_street_level_crimes | Retrieve street-level crimes by lat/lng or custom polygon area |
| get_street_level_outcomes | Retrieve outcomes by lat/lng, custom polygon, or location ID |
| get_crimes_at_location | Retrieve crimes at a specific location by ID or nearest to lat/lng |
| get_crimes_no_location | Retrieve crimes that could not be mapped to a location |
| get_crime_categories | Retrieve valid crime categories for a given date |
| get_last_updated | Retrieve the date when crime data was last updated |
| get_outcomes_for_crime | Retrieve outcomes for a specific crime by persistent ID |
| get_list_of_forces | Retrieve a list of all police forces |
| get_force_details | Retrieve details for a specific police force |
| get_senior_officers | Retrieve senior officers for a specific police force |
| get_neighbourhoods | Retrieve a list of neighbourhoods for a specific police force |
| get_neighbourhood_details | Retrieve details for a specific neighbourhood within a force |
| get_neighbourhood_boundary | Retrieve the boundary coordinates for a specific neighbourhood |
| get_neighbourhood_team | Retrieve the team members for a specific neighbourhood |
| get_neighbourhood_events | Retrieve events scheduled for a specific neighbourhood |
| get_neighbourhood_priorities | Retrieve policing priorities for a specific neighbourhood |
| locate_neighbourhood | Find the neighbourhood policing team for a given latitude and longitude |
| get_stop_searches_by_area | Retrieve stop and searches within a 1-mile radius or custom area |
| get_stop_searches_by_location | Retrieve stop and searches at a specific location by ID |
| get_stop_searches_no_location | Retrieve stop and searches that could not be mapped to a location |
| get_stop_searches_by_force | Retrieve stop and searches reported by a specific force |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659577859](https://mcp.xiaobenyang.com/inspector/1777316659577859)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659577859](https://mcp.xiaobenyang.com/inspector/1777316659577859)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "警察数据查询服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659577859/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "警察数据查询服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659577859/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "警察数据查询服务": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659577859",
          },
          "transport": "stdio"
        }
      }
}

```
