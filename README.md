%%{init: {'theme':'base', 'themeVariables':{ 'primaryColor':'#4A90D9','primaryTextColor':'#fff','primaryBorderColor':'#2C5F8A','lineColor':'#2C5F8A','secondaryColor':'#E8F0FE'}}}%%
flowchart LR
    User(["👤 普通用户"])

    subgraph System["🖥️ 基于大数据的网络舆情情感分析系统"]
        UC1["📂 UC1: 导入舆情数据<br/>（支持CSV格式上传）"]
        UC2["📊 UC2: 查看情感分析结果<br/>（饼图/折线图/词云图）"]
        UC3["🔍 UC3: 检索/筛选数据<br/>（按时间/情感类别/关键词）"]
        UC4["📥 UC4: 导出分析报表<br/>（导出为Excel文件）"]
        UC5["🗑️ UC5: 删除数据记录<br/>（删除单条评论）"]
    end

    User --> UC1
    User --> UC2
    User --> UC3
    User --> UC4
    User --> UC5

    UC3 -.->|"<<extend>> 检索后查看详细结果"| UC2
    UC2 -.->|"<<include>> 查看时可删除错误数据"| UC5

    Note["📝 本系统仅设普通用户角色<br/>无需管理员权限<br/>用户可完成全部操作"]
    User --- Note

