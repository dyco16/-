```mermaid
%%{init: {'theme':'base', 'themeVariables':{ 'primaryColor':'#4A90D9','primaryTextColor':'#fff','primaryBorderColor':'#2C5F8A','lineColor':'#2C5F8A','secondaryColor':'#E8F0FE','tertiaryColor':'#fff'}}}%%
usecaseDiagram
    actor "普通用户" as User

    package "基于大数据的网络舆情情感分析系统" {
        usecase "UC1: 导入舆情数据\n（支持CSV格式上传）" as UC1
        usecase "UC2: 查看情感分析结果\n（饼图/折线图/词云图）" as UC2
        usecase "UC3: 检索/筛选数据\n（按时间/情感类别/关键词）" as UC3
        usecase "UC4: 导出分析报表\n（导出为Excel文件）" as UC4
        usecase "UC5: 删除数据记录\n（删除单条评论）" as UC5
    }

    User --> UC1
    User --> UC2
    User --> UC3
    User --> UC4
    User --> UC5

    UC3 ..> UC2 : <<extend>>\n检索后查看详细结果
    UC2 ..> UC5 : <<include>>\n查看时可删除错误数据

    note right of User
        本系统仅设普通用户角色，
        无需管理员权限。用户可完成
        数据导入、分析查看、检索、
        导出及删除等全部操作。
    end note
```
