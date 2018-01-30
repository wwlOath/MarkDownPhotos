## 一、SurvivalViewer app
![image]()
### 1.1、URL
    getDatasetSurvivalResult
### 1.2、参数
    dataset_id: 'DWXSGC0176',
    geneSite: '',
    stype: 'gene',
    category: 'somatic',
    mut_number: 1,
    mut_number_filter: '>=',
    non_mut_number: 1,
    non_mut_number_filter: '>=',
    pvalue: 0.05,
    pvalue_filter: '<=',
    coef: '',
    coef_filter: '',
### 1.3 成功时返回
    {
        data: [
            ["DWXSGC0176", "MSRB1", "", "gene", "somatic", 1, 7, 0.00815097159350275, -22.0037111632697, 7],
            ["DWXSGC0176", "PCDHB15", "", "gene", "somatic", 1, 7, 0.00815097159350275, -22.0037111632697, 7],
            ...
        ],
        header: ["dataset_id","gene","site","stype","category","mut_number","non_mut_number","pvalue","coef","logrank_stat"],
        type: "success"
    }
### 1.4 失败时返回
    {
        type: 'nodata'
    }
    
### 2.1 URL
    