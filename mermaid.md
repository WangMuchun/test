graph TB
    %% 定义样式
    classDef mainNode fill:#ffcccc,stroke:#cc0000,stroke-width:2px,color:#000000,font-weight:bold;
    classDef branchNode fill:#ffffff,stroke:#333333,stroke-width:1px,color:#000000;
    classDef approvalNode fill:#e6f3ff,stroke:#0055aa,stroke-width:1.5px,color:#000000,stroke-dasharray: 5 5;

    %% 1. 左侧主干列 (红轴)
    A[1. 项目建议书]:::mainNode
    B[2. 可行性研究报告]:::mainNode
    K[3. 初步设计]:::mainNode
    N[4. 施工图设计]:::mainNode
    Q[5. 施工前准备]:::mainNode
    U[6. 施工及设备安装]:::mainNode
    W[7. 试运行]:::mainNode
    Y[8. 竣工验收]:::mainNode
    Z[9. 备案及工程移交]:::mainNode
    AA[10. 项目后评价]:::mainNode

    %% 2. 右侧分支列 (白轴 - 包含新增的审批手续)
    
    %% A - 项目建议书阶段
    C1[签订可研委托合同]:::branchNode
    C2[★ 取得选址意见书]:::approvalNode

    %% B - 可研阶段
    C3[确定投资估算]:::branchNode
    C4[★ 取得用地预审与选址意见]:::approvalNode
    C5[向园林/人防报审方案]:::branchNode
    C6[★ 环评/水保/节能审批]:::approvalNode
    C7[委托设计/勘察]:::branchNode
    C8[★ 取得用地规划许可证]:::approvalNode

    %% K - 初步设计
    C9[确定投资概算]:::branchNode
    C10[★ 取得建设工程规划许可证]:::approvalNode
    C11[★ 消防/人防/绿化专项审查]:::approvalNode

    %% N - 施工图设计
    C12[确定投资预算]:::branchNode
    C13[★ 施工图审查合格证]:::approvalNode

    %% Q - 施工前准备
    C14[施工招标]:::branchNode
    C15[★ 办理施工许可证]:::approvalNode
    C16[★ 办理质量/安全监督手续]:::approvalNode
    C17[设备/材料采购]:::branchNode

    %% U - 施工及设备安装
    C18[★ 隐蔽工程验收]:::approvalNode
    C19[★ 分部分项验收]:::approvalNode
    C20[★ 特种设备检测]:::approvalNode

    %% W - 试运行
    C21[预验收]:::branchNode
    C22[★ 消防/环保/规划专项验收]:::approvalNode

    %% Y - 竣工验收
    C23[竣工决算]:::branchNode
    C24[★ 工程质量竣工验收]:::approvalNode

    %% 3. 主干连接
    A --> B --> K --> N --> Q --> U --> W --> Y --> Z --> AA

    %% 4. 右侧分支列纵向对齐 (隐形连线)
    C1 ~~~ C2 ~~~ C3 ~~~ C4 ~~~ C5 ~~~ C6 ~~~ C7 ~~~ C8
    C8 ~~~ C9 ~~~ C10 ~~~ C11
    C11 ~~~ C12 ~~~ C13
    C13 ~~~ C14 ~~~ C15 ~~~ C16 ~~~ C17
    C17 ~~~ C18 ~~~ C19 ~~~ C20
    C20 ~~~ C21 ~~~ C22
    C22 ~~~ C23 ~~~ C24

    %% 5. 横向连接：主干 → 右侧分支
    A --> C1 & C2
    B --> C3 & C4 & C5 & C6 & C7 & C8
    K --> C9 & C10 & C11
    N --> C12 & C13
    Q --> C14 & C15 & C16 & C17
    U --> C18 & C19 & C20
    W --> C21 & C22
    Y --> C23 & C24
