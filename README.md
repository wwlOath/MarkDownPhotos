## 一、SurvivalViewer app
![image](https://github.com/wwlOath/MarkDownPhotos/blob/master/1.png?raw=true)

### 1、Dataset Survival Result List
![image](https://github.com/wwlOath/MarkDownPhotos/blob/master/2.png?raw=true)
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
    
### 2、Survival Compare Tool
![image](https://github.com/wwlOath/MarkDownPhotos/blob/master/3.png?raw=true)
### 2.1.1 URL
    survival
### 2.1.2 参数
    dataIdType: 'dataset',
    specimenType: 'case',
    data: 'DWXSGC0176',
    geneIdType: 'gene',
    gene: 'GRIN2C',
    somaticOrGermline: 'somatic',
### 2.1.3 成功时返回
    {
        category: ["No Mutation","No Mutation","No Mutation","No Mutation","No Mutation","No Mutation","Mutation","No Mutation"],
        event: ["1","1","1","1","1","1","1","1"],
        msg: 'success',
        sample: ["SWXS0004254","SWXS0004257","SWXS0004260","SWXS0004263","SWXS0004266","SWXS0004269","SWXS0004272","SWXS0004275"],
        time: ["3.6","16.6","19.6","31.4","54.7","5.3","4.5","13"],
        type: 'success'
    }
### 2.1.4 失败时返回
    {
        msg: 'found no data!',
        type: 'error',
    }
    
### 2.2.1 URL
    survivalDelverToRCompute
### 2.2.2 参数
    content:{
        "time":["3.6","16.6","19.6","31.4","54.7","5.3","4.5","13"],
        "sample":["SWXS0004254","SWXS0004257","SWXS0004260","SWXS0004263","SWXS0004266","SWXS0004269","SWXS0004272","SWXS0004275"],
        "event":["1","1","1","1","1","1","1","1"],
        "category":["No Mutation","No Mutation","No Mutation","No Mutation","No Mutation","No Mutation","Mutation","No Mutation"],
        "type":"success",
        "msg":"success"
    }
### 2.2.3 成功时返回
    {
        "dof": 1,
        "KM_stats": 2.312242,
        "pValue": 0.12835878,
        "type": "success",
    }

## 二、RegulatorPathNet app
![image](https://github.com/wwlOath/MarkDownPhotos/blob/master/5.png?raw=true)
    
### 1、RegulatorPathNet
![image](https://github.com/wwlOath/MarkDownPhotos/blob/master/6.png?raw=true)
### 1.1 URL
    checkOutAnalysisStatusForAppRegulatorPathNet
### 1.2 参数
    statusInfo:[
        {
            "analysisId":"6e8a0879-9e5d-48e1-9692-d34d2d9d1d4f",
            "analysisStatus":"warning"
        
        },
        {
            "analysisId":"a7b0f0da-4dbe-4a32-991e-47ad3bb27bcf",
            "analysisStatus":"runing"
            
        }
    ]
### 1.3 成功时返回
    {
        "msg": "success",
        "content":{
            "6e8a0879-9e5d-48e1-9692-d34d2d9d1d4f":["1","warning","Found no differently expressed genes, may be cuased by too strict paramerters"],
            "a7b0f0da-4dbe-4a32-991e-47ad3bb27bcf":["0.8","runing","run correlation analysis"]
        }
    }
    
### 2、RegulatorPathNet Visual
![image](https://github.com/wwlOath/MarkDownPhotos/blob/master/7.png?raw=true)
### 2.1.1 URL
    queryAnalysisResult
### 2.1.2  参数
    analysisId: fbe86f4a-5b4d-4ed5-b7a7-887456d11db8
### 2.1.3 成功时返回
    {
        "header":{
            "message": "success",
            "statusCode": 200
        },
        "content":{
            "analysisDescription": "",
            "analysisId": "fbe86f4a-5b4d-4ed5-b7a7-887456d11db8",
            "analysisName": "RNA-seq of two paired normal and cancer tissues in two stage III colorectal cancer patients",
            "analysisParameters": {
                "data": {
                    "case": ["SRNA0001077", "SRNA0001079"],
                    "control": ["SRNA0001076", "SRNA0001078"]
                },
                "ref": "case",
                "method": "DESeq2",
                "pvalue": "0.01",
                "fdr": "0.02",
                "fc": "2"
            },
            "analysisStatus": "complete",
            "appId": "RegulatorPathNet",
            "appName": "RegulatorPathNet",
            "createTime":{
                "date":2,"day":6,"hours":17,"minutes":50,"month":8,"nanos":0,"seconds":24,"time":1504345824000,"timezoneOffset":-480,"year":117
            },
            "userEmail":"yonghui.gong@myhealthgene.com",
            "userId":"2d8eefb9-ecc6-495e-86ad-260b3bed0864"
        }
    }
    
### 2.2.1 URL
    regulatoryPathNetGetresult
### 2.2.2 参数
    analysisId: 027bd1f1-d2f6-49e4-bb67-39a20d8c45bd
### 2.2.3 成功时返回
    {
        corgenes: [
            ["ALDH3A1", "ADH1B", "0.30527207203668", "0.361313305367523"],
            ["IMPDH1", "NT5C3B", "0.825947569529396", "0.00173213588253135"],
            ...
        ],
        corgenes_header: ["gene", "gene", "co-expression", "pValue"],
        degenes: [
            ["ESM1", "-4.40732842406478", "5.65680569461511e-18", "9.86660049254768e-14"],
            ["C2orf40", "4.80147877631271", "2.6650459052181e-16", "2.3241865339407e-12"],
            ...
        ],
        degenes_header: ["gene", "log2FC", "pValue", "fdr"],
        enrichedkeggpathway: [
            ["ID", "Description", "BgRatio", "pvalue", "p.adjust"],
            ["hsa05146", "NA", "106/5894", "5.35277983977723e-06", "0.000865019211317007"],
            ...
        ],
        enrichedkeggpathway_header: ["pathwayId", "pathwayName", "bgRatio", "pValue", "fdr"],
        msg: "success",
    }
### 2.3.1 URL
    queryPathwayGeneRelation
### 2.3.2 参数
    pathwayIds: '',
    geneSymbols: 'BEST4,OTOP2,CA7,...'  
### 2.3.3 成功时返回
    {
        header: {
            message: 'success',
            statusCode: 200
        },
        content: [
            {
                downGeneEntrez: '',
                downGeneSymbol: 'CDH3',
                downMapRect: '',
                geneRelation: 'binding/association',
                geneRelationType: 'unkown',
                pathwayId: 'hsa04514',
                pathwayName: 'Cell adhesion molecules (CAMs)',
                upGeneEntrez: '',
                upGeneSymbol: 'CDH3',
                upMapRect: '',
            },
            ...
        ]
    }
    
## 三、GExPattern app
![image](https://github.com/wwlOath/MarkDownPhotos/blob/master/8.png?raw=true)

### 1、GExPattern
![image](https://github.com/wwlOath/MarkDownPhotos/blob/master/9.png?raw=true)
### 3.1.1 URL
    makeExpDataForHistogramPlotByGeneName
### 3.1.2 参数
    geneSymbol: 'PTEN'
### 3.1.3 成功时返回
    {
        "specimenTypes": ["control","case"],
        "primaryTissueSite": ["Stomach","Colorectum","Colon","esophagus","Esophagus"],
        "expDataMatrix": [[5455,1447,1508,1741,733],[4797,1270,1917,1812,778]],
        "result": "success"
    }
### 3.2.1 URL
    runGExPattern
### 3.2.2 参数
    searchType: 'specimenId',
    specimenIds: 'SRNA0001085'
                 'SRNA0001094'
                 'SRNA0001103'
                 'SRNA0001112',
    primaryTissueSite: 'Liver',
    primaryTissueSite: 'Colorectum',
    geneSymbolList: 'CA7'
                    'BEST4'
                    'AQP8'
                    'GUCA2B'
                    'CA4'
### 3.2.3 成功时返回
    {
        datamatrix: [
            ["3.700439718141092", "3.1699250014423126", "6.643856189774725", "4.700439718141093", "5.906890595608519", "8.618385502258606", "6.169925001442312", "9.751544059089097", "2.807354922057604", "5.169925001442312", "4.247927513443585", "4.08746284125034", "4.247927513443585", "5.20945336562895", "9.383704292474052", "8.519636252843213", "5.523561956057013", "2.0", "11.005624549193877", "10.64565843240871", "11.476239906323851", "10.928518375257891", "10.129283016944967", "11.338179249900112", "11.946540803893104", "10.755722153642283", "11.914011328541255", "12.202736043250168", "11.449664538476192", "11.413098984915264", "12.26532202423487", "11.32023644524165", "11.302067672526519", "12.105253779700885", "10.191059214531656", "12.477758266443887"],
            ["0.0", "2.0", "7.965784284662087", "0.0", "8.169925001442312", "10.659103963473662", "10.005624549193877", "11.65150022065274", "3.3219280948873626", "1.5849625007211563", "3.3219280948873626", "6.044394119358453", "5.672425341971496", "6.22881869049588", "11.680799034572983", "9.848622940429339", "7.10852445677817", "2.0", "11.018200178813226", "11.029287226968245", "11.62890115202819", "11.51668494930961", "9.88264304936184", "11.778487861222372", "10.703903573444665", "11.233020426474496", "11.551227603598289", "12.713601313573752", "12.635718120331047", "11.459431618637298", "11.969386521342281", "11.787902559391433", "9.588714635582264", "12.374767814092824", "12.19383333254655", "10.915879378835774"],
            ...
        ],
        gene: ["BEST4", "TMIGD1", "CXCL8", "AQP8", "CA4", "CA7", "GUCA2B", "INHBA", "CLDN1", "ETV4", "GUCA2A", "CTHRC1"],
        specimen: ["SRNA0001102", "SRNA0001091", "SRNA0001090", "SRNA0001093", "SRNA0001092", "SRNA0001095", "SRNA0001094", "SRNA0001097", "SRNA0001096", "SRNA0001099", "SRNA0001098", "SRNA0001086", "SRNA0001085", "SRNA0001088", "SRNA0001087", "SRNA0001101", "SRNA0001089", "SRNA0001100", "SRNA0001104", "SRNA0001112", "SRNA0001111", "SRNA0001114", "SRNA0001113", "SRNA0001116", "SRNA0001115", "SRNA0001118", "SRNA0001117", "SRNA0001119", "SRNA0001107", "SRNA0001106", "SRNA0001109", "SRNA0001108", "SRNA0001120", "SRNA0001103", "SRNA0001105", "SRNA0001110"],,
        specimenTissue: ["Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum", "Colorectum"],
        specimenType: ["case", "case", "case", "case", "case", "case", "case", "case", "case", "case", "case", "case", "case", "case", "case", "case", "case", "case", "control", "control", "control", "control", "control", "control", "control", "control", "control", "control", "control", "control", "control", "control", "control", "control", "control", "control"],
        resultType: 'success',
    }
    
### 四、OmicsFeatureViewer app
![image](https://github.com/wwlOath/MarkDownPhotos/blob/master/10.png?raw=true)

### 1、OmicsFeatureViwewe
![image](https://github.com/wwlOath/MarkDownPhotos/blob/master/11.png?raw=true)
### 4.1.1 URL
    queryExpressionDepth
### 4.1.2 参数
    specimenIds:{
        "SRNA0003386": "",
        "SRNA0003387": "",
        "SRNA0003385": "",
    },
    geneSymbol: 'TP53',
    tagFlag: false,
### 4.1.3 成功时返回
    {
        "header":{
            "message":"success",
            "statusCode":200
        },
        "exp":[
            {
                "name": "control",
                "exp": [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,…],
                "specimen": ["SRNA0003387","SRNA0003386"],
            },
            {
                "name": "case",
                "exp": [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,…],
                "specimen": ["SRNA0003387", "SRNA0003386"],
            }
        ]
    }
### 4.2.1 URL
    queryGeneExonsStructure
### 4.2.2 参数
    geneSymbol: 'TP53'
### 4.2.3 成功时返回
    {
        header: {
            message: "success",
            statusCode: 200
        },
        content: {
            chr: 'chr17',
            e_0: 25759,
            end: '7590856',
            ensembl: {
                structure_hg19: [
                    {
                        exons: [
                            {e_0: 1783, s_0: 495, type: "exon", end: "7573008", start: "7571720"},
                            {e_0: 1940, s_0: 1834, type: "exon", end: "7574033", start: "7573927"},
                            ....
                        ],
                        transcript: 'ENST00000504937',
                    },
                    ...
                ]
            },
            entrez_id: '7157',
            name: 'TP53',
            s_0: 0,
            sequence: 'gagacagagtctcactctgttgcacaggctggagtgcagtggcacaatctctgctcactgcaacctcctcctccctggttaagagatcctcctgcctcagcccccttagtagctgggattacaggcgtgggccaccactgccaggctaatttttgtatttttagtagagatgggatttcgctatgttggccaggctgtcttgaactcctgacctcaggtgatccacctgccttggcctAAAGAGAGAGAGAgagacggagttttcttccatttttttttcttttttgagatggagtcttgctctgttgcccaggctagagtgcaatggcgcaatctcggctcactgcaaccctctgcctcctgggttcaagcgattctcctgcctcagcctcccgagtagctgggattacaggtgtgatccaccgtgcctggcCGGAAATGTTTTCTAAATAAAAAAATAGAACATATTGGACCCCAGTAGCCTGCACTGGCGTTCACCCCTCAGACACACAGGTGGCAGCAAAGTTTTATTGTAAAATAAGAGATCGATATAAAAATGGGATATAAAAAGGGAGAAGGAGGGGAAGGGTGGGGTGAAAATGCAGATGTGCTTGCAGAATGTAAAAGATGTTGACCCTTCCAgctggacgtggtggctcacaattgtaatcccagcactctgggaggctgagacaggtggatcgcctgagcccaggagtttgagaccagcctgggcaacactgtgagaccccatctctacaaaacatgcaaaagttggctggccatggtggcatgaacctgtggtcccagctactccggaggctgaggcaggactgctcgagccggggaggcaaaggctgcagtaagccaagatcacgccactccactccagcctgggcaacaaagcgagacccagtctcaaagaaaaagaaaaaaaaaaaaaaaaaagaaaaaagaaaTTGACCCTGAGCATAAAACAAGTCTTGGTGGATCCAGATCATCATATACAAGAGATGAAATCCTCCAGGGTGTGGGATGGGGTGAGATTTCCTTTTAGGTACTAAGGTTCACCAAGAGGTTGTCAGACAGGGTTTGGCTGGGCCAGCAGAGACTTGACAACTCCCTCTACCTAACCAGCTGCCCAACTGTAGAAACTACCAACCCACCGACCAACAGGGAGAGGGAACAAGCACCCTCAAGGGGGTCAAGTTCTAGACCCCATGTAATAAAAGGTGgtttcaaggccagatgtacattatttcattaaccctcacaatgcactctgtgaggtaggtgcaaatgccagcatttcacagatatgggccttgaagttagagaAAATTCAACAGTGAGGGACAGCTTCCCTGGTTAGTACGGTGAAGTGGGCCCCTACCTAGAATGTGGCTGATTGTAAACTAACCCTTAACTGCAAGAACATTTCTTACATCTCCCAAACATCCCTCACAGTAAAAACCTTAAAATCTAAGCTGGTATGTCCTACTCCCCATCCTCCTCCCCACAACAAAACACCAGTGCAGGCCAACTTGTTCAGTGGAGCCCCGGGACAAAGCAAATGGAAGTCCTGGGTGCTTCTGACGCACACCTATTGCAAGCAAGGGTTCAAAGACCCAAAACCCAAAATGGCAGGGGAGGGAGAGATGGGGGTGGGAGGCTGTCAGTGGGGAACAAGAAGTGGAGAATGTCAGTCTGAGTCAGGCCCTTCTGTCTTGAACATGAGTTTTTTATGGCGGGAGGTAGACTGACCCTTTTTGGACTTCAGGTGGCTGTAGGAGACAGAAGCAGGGAGGACCAGGAAGGGGCTGAGGTCACTCACCTGGAGTGAGCCCTGCTCCCCCCTGGCTCCTTCCCAGCCTGGGCATCCTTGAGTTCCAAGGCCTCATTCAGCTCTCGGAACATCTCGAAGCGCTCACGCCCACGGATCTGCAGCAACAGAGGAGGGGGAGAAtgtattaaatccattttcaacttacaatattttcaacttacgacgagtttatcaggaagtaacaccatcgtaagtcaagtagcatctgTATCAGGCAAAGTCATAGAACCATTTTCATGCTCTCTTTAACAATTTTCTTTTTGAAAGCTGGTCTGGTCCTTTAAAATATATATTATGGTATAAGATAAGAGGTCCCAAGACTTAGTACCTGAAGGGTGAAATATTCTCCATCCAGTGGTTTCTTCTTTGGCTGGGGAGAGGAGCTGGTGTTGTTGGGCAGTGCTAGGAAAGAGGCAAGGAAAGGTGAACCGCTTCTTGTCCTGCTTGCTTACCTCGCTTAGTGCTCCCTGGGGGCAGCTCGTGGTGAGGCTCCCCTTTCTTGCGGAGATTCTCTTCCTCTGTGCGCCGGTCTCTCCCAGGACAGGCACAAACACGCACCTCAAAGCTGTTCCGTCCCAGTAGATTACCACTACTCAGGATAGGAAAAGAGAAGCTGCAGGGTGGCAAGTGGCTCCTGACCTGGAGTCTTCCAGTGTGATGATGGTGAGGATGGGCCTCCGGTTCATGCCGCCCATGCAGGAACTGTTACACATGTAGTTGTAGTGGATGGTGGTACAGTCAGAGCCAACCTAGGAGATAACACAGGCCCAAGATggtgcccagcaccacgcccggctaatttttttttgtatttttcagtagagacggggtttcaccgttagccaggatggtctcgatctcccaacctcgtgatccgcctgccttggcctcccaaagtgctgggattacaggcatgagccactgcgcccagccAAGCAGGGGaggcccttagcctctgtaagcttcagttttttcaactgtgcaatagttaaacccatttactttgcacatctcatggggttatagggaggtcaaataagCAGCAGGAGAAAGCCCCCCTACTGCTCACCTGGAGGGCCACTGACAACCACCCTTAACCCCTCCTCCCAGAGACCCCAGTTGCAAACCAGACCTCAGGCGGCTCATAGGGCACCACCACACTATGTCGAAAAGTGTTTCTGTCATCCAAATACTCCACACGCAAATTTCCTTCCACTCGGATAAGATGCTGAGGAGGGGCCAGACCTAAGAGCAATCAGTGAGGAATCAGCGTCTCTCCAGCCCCAGCTGCTCACCATCGCTATCTGAGCAGCGCTCATGGTGGGGGCAGCGCCTCACAACCTCCGTCATGTGCTGTGACTGCTTGTAGATGGCCATGGCGCGGACGCGGGTGCCGGGCGGGGGTGTGGAATCAACCCACAGCTGCACAGGGCAGGTCTTGGCCAGTTGGCAAAACATCTTGTTGAGGGCAGGGGAGTACTGTAGGAAGAGGAAGGAGACAGAGTTGAAAGTCAGGGCACAAGTGAACAGATAAAGCAACTGGAAGACGGCAGCAAAGAAACAAACATGCGTAAGCACCTCCTGCAACCCACTAGCGAGCTAGAGAGAGTTGGCGTCTACACCTCAGGAGCttttcttttttttttttttttttgagatagggtcttgctctgtcactcaggctggagcacagtggtgtgatcacagctcactgcagcctccatctcctggcctcaagtgatcttcccacctcagcctcctAAGCCAGCCCCTCAGGGCAACTGACCGTGCAAGTCACAGACTTGGCTGTCCCAGAATGCAAGAAGCCCAGACGGAAACCGTAGCTGCCCTGGTAGGTTTTCTGGGAAGGGACAGAAGATGACAGGGGCCAGGAGGGGGCTGGTGCAGGGGCCGCCGGTGTAGGAGCTGCTGGTGCAGGGGCCACGGGGGGAGCAGCCTCTGGCATTCTGGGAGCTTCATCTGGACCTGGGTCTTCAGTGAACCATTGTTCAATATCGTCCGGGGACAGCATCAAATCATCCATTGCTTGGGACGGCAAGGGGGACTGTAGATGGGTGAAAAGAGCAGTCtccccagcccAACCCTTGTCCTTACCAGAACGTTGTTTTCAGGAAGTCTGAAAGACAAGAGCAGAAAGTCAGTCCCATGGAATTTTCGCTTCCCACAGGTCTCTGCTAGGGGGCTGGGGTTGGGGTGGGGGTGGTGGGCCTGCCCTTCCAATGGATCCACTCACAGTTTCCATAGGTCTGAAAATGTTTCCTGACTCAGAGGGGGCTCGACGCTAGGATCTGACTGCGGCTCCTCCATGGCAGTGACCCGGAAGGCAGTCTGGCTGCTGCAAGAGGAAAAGTGGGGATCCACCCCTTGGCCCCCACCCTTCCCCACCTGATACACGGCTCCATTTCTTTGATTCCTTTCACTGCAAAGCTTCTGGAAGAACAACTGTCTCACCGCTCACCTGCCCATTCTCTTCGGACACTCCTCAGCCCTGCATTACAAACCCCTCACGAATGGCCCGTCTCATCAAGTTCAGTCAGGAGCTTACCCAATCCAGGGAAGCGTGTCACCGTCGTGGAAAGCACGCTCCCAGCCCGAACGCAAAGTGTCCCCGGAGCCCAGCAGCTACCTGCTCCCTGGACGGTGGCTCTAGACTTTTGAGAAGCTCAAAACTTTTAGCGCCAGTCTTGAGCACATGGGAGGGGAAAAC',
            start: '7565097',
            type: 'protein_coding',
        }
    }
    
### 五、Cancer Report app
![image](https://github.com/wwlOath/MarkDownPhotos/blob/master/12.png?raw=true)

### 1、Cancer Report
![image](https://github.com/wwlOath/MarkDownPhotos/blob/master/13.png?raw=true)
### 5.1 URL
    omicsPanCancerReport
### 5.2 参数
    genes: 'PRIM2,PRKDC,ING3,TP53,AR,PIK3CA',
    specimens: '',
    time: Tue Jan 30 2018 14:14:31 GMT+0800 (中国标准时间)
### 5.3 成功时返回
    {
        data: [
            ["AR", "", "", "", "Y", "", "Y", "", "", "", "", "", "", "", "", "", "", "", "", 5, 5, "1.000", 5, 5, "1.000", 1, 5, "0.200", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", 1, 14, "0.071", "", "", "", "", "", "", "", "", "", 12, 14, "0.857", 14, 14, "1.000", "", "", "", 1, 14, "0.071", 1, 14, "0.071", "", "", "", "", "", "", 1, 14, "0.071", "", "", "", "", "", "", 2, 18, "0.111", "", "", "", "", "", "", "", "", "", 10, 18, "0.556", 10, 18, "0.556", "", "", "", "", "", "", 1, 18, "0.056", "", "", "", "", "", "", "", "", "", "", "", "", "", "", ""],
            ["ING3", "", "", "", "", "", "", "", "", "", "", "", "", "", "", ["ING3", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", 2, 5, "0.400", 5, 5, "1.000", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", 1, 5, "0.200", "", "", "", 5, 5, "1.000", "", "", "", "", "", "", "", "", "", "", "", "", 3, 14, "0.214", 14, 14, "1.000", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", 1, 14, "0.071", "", "", "", 14, 14, "1.000", "", "", "", "", "", "", "", "", "", "", "", "", 5, 18, "0.278", 9, 18, "0.500", "", "", "", "", "", "", 3, 18, "0.167", "", "", "", "", "", "", "", "", "", "", "", "", 8, 18, "0.444"],
            ...
        ],
        primaryTissueSites: ["Colon", "Colorectum", "Stomach"],
        specimenChooseType: 'all',
        variationTypes: ["UTR3", "UTR5", "downstream", "frameshift deletion", "intergenic", "intronic", "nonframeshift deletion", "nonframeshift insertion", "nonsynonymous SNV", "splicing", "stopgain", "synonymous SNV", "unknown", "upstream"],
    }

### 六、Mutation Mapper app
![image](https://github.com/wwlOath/MarkDownPhotos/blob/master/14.png?raw=true)

### 1、Mutation Mapper
![image](https://github.com/wwlOath/MarkDownPhotos/blob/master/15.png?raw=true)
### 6.1.1 URL
    askDataForMutationMapper
### 6.1.2 参数
    geneName: 'PTEN',
    specimens: '',
### 6.1.3 成功时返回
    {
	    "specimenChooseType": "all",
	    "resultType": "success",
        "result": {
	            "header": ["mutation_id", "primary_tissue_site", "specimen_type", "rs_id", "Hugo_Symbol", "Mutation_Type", "cds_change", "Protein_Change", "disease_name", "clinical_significance", "pubmeds", "mut_Speciments", "all_Speciments", "mutation_Rate", "tcga.HNSC", "cosmic.cervix", "cosmic.genital_tract", "tcga.LUAD", "tcga.UCEC", "exac.id", "1000g.AFR", "cosmic.pituitary", "tcga.KIRP", "1000g.id", "cosmic.bone", "tcga.TGCT", "cosmic.testis", "cosmic.soft_tissue", "cosmic.gastrointestinal_tract_site_indeterminate", "tcga.CESC", "cosmic.oesophagus", "esp.id", "tcga.PAAD", "cosmic.fallopian_tube", "exac.south_asian_rate", "exac.east_asian_rate", "cosmic.small_intestine", "cosmic.lung", "cosmic.NS", "cosmic.central_nervous_system", "tcga.PCPG", "cosmic.stomach", "cosmic.adrenal_gland", "1000g.total_rate", "tcga.BRCA", "tcga.UVM", "esp.european_american_population_rate", "cosmic.total_average", "cosmic.thyroid", "cosmic.thymus", "tcga.PRAD", "tcga.STAD", "tcga.SARC", "1000g.SAS", "cosmic.placenta", "cosmic.mutation_id", "cosmic.penis", "tcga.LGG", "1000g.EAS", "tcga.OV", "tcga.BLCA", "tcga.CHOL", "cosmic.large_intestine", "cosmic.pericardium", "tcga.SKCM", "exac.all_ethnicity_rate", "1000g.AMR", "cosmic.pleura", "cosmic.breast", "tcga.GBM", "tcga.ESCA", "cosmic.prostate", "cosmic.paratesticular_tissues", "cosmic.eye", "cosmic.haematopoietic_and_lymphoid_tissue", "cosmic.parathyroid", "tcga.ACC", "cosmic.endometrium", "tcga.KIRC", "cosmic.retroperitoneum", "cosmic.urinary_tract", "tcga.THCA", "cosmic.autonomic_ganglia", "tcga.mutation_id", "tcga.MESO", "cosmic.ovary", "1000g.EUR", "cosmic.peritoneum", "tcga.LUSC", "cosmic.kidney", "cosmic.salivary_gland", "tcga.totalagvrate", "tcga.LAML", "tcga.KICH", "tcga.READ", "tcga.THYM", "cosmic.upper_aerodigestive_tract", "cosmic.meninges", "tcga.DLBC", "tcga.COAD", "cosmic.liver", "esp.african_american_population_rate", "cosmic.biliary_tract", "cosmic.skin", "exac.asian_rate", "cosmic.vagina", "tcga.LIHC", "esp.total_population_rate", "cosmic.pancreas", "cosmic.vulva", "1000g.rs_id", "tcga.UCS"],
		    "body": [
			["10:89623716:G:A", "Stomach", "case", "rs12573787", "PTEN", "nonsynonymous SNV", "c.G10A", "p.G4R", ".", ".", ".", "1", "18", "0.0556", "", "", "", "", "", "", 0.1059, "", "", null, "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", 0.28435, "", "", "", "", "", "", "", "", "", 0.23722, "", "", "", "", 0.55754, "", "", "", "", "", "", "", 0.35735, "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", 0.24056, "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "rs12573787", ""],
			["10:89623716:G:A", "Stomach", "control", "rs12573787", "PTEN", "nonsynonymous SNV", "c.G10A", "p.G4R", ".", ".", ".", "1", "18", "0.0556", "", "", "", "", "", "", 0.1059, "", "", null, "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", 0.28435, "", "", "", "", "", "", "", "", "", 0.23722, "", "", "", "", 0.55754, "", "", "", "", "", "", "", 0.35735, "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", 0.24056, "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "", "rs12573787", ""],
		   ...
		]
	}
### 6.2.1 URL
    getPfamSequence
### 6.2.2 参数
    geneSymbol: 'PTEN'
### 6.2.3 成功时返回
    [{"length": 403,
	  "regions": [{
		  "modelStart": 59,
		  "modelEnd": 114,
		  "colour": "#2dcf00",
		  "endStyle": "jagged",
		  "end": 173,
		  "display": null,
		  "startStyle": "jagged",
		  "aliEnd": 159,
		  "modelLength": 133,
		  "text": "DSPc",
		  "href": "/family/PF00782",
		  "type": "pfama",
		  "metadata": {
			  "scoreName": "e-value",
			  "score": "0.0004",
			  "description": "Dual specificity phosphatase, catalytic domain",
			  "end": 173,
			  "accession": "PF00782",
			  "database": "pfam",
			  "identifier": "DSPc",
			  "aliEnd": 159,
			  "type": "Domain",
			  "aliStart": 101,
			  "start": 67
		  },
		  "aliStart": 101,
		  "start": 67
	  }, 
	  ...
	  ],
	  "markups": [{
		  "lineColour": "#333333",
		  "colour": "#ff4848",
		  "display": null,
		  "residue": "C",
		  "headStyle": "diamond",
		  "v_align": "top",
		  "type": "Active site",
		  "metadata": {
			  "database": "UniProt",
			  "description": "C Active site:Phosphocysteine intermediate",
			  "start": 124
		  },
		  "start": 124
	  }, 
	  ...
	  ],
	  "metadata": {
		  "database": "uniprot",
		  "identifier": "PTEN_HUMAN",
		  "organism": "Homo sapiens (Human)",
		  "description": "Phosphatidylinositol 3,4,5-trisphosphate 3-phosphatase and dual-specificity protein phosphatase PTEN EC=3.1.3.16 EC=3.1.3.48 EC=3.1.3.67",
		  "taxid": "9606",
		  "accession": "P60484"
	  },
	  "motifs": [{
		  "colour": "#00ffff",
		  "type": "disorder",
		  "metadata": {
			  "database": "IUPred",
			  "type": "disorder",
			  "start": 290,
			  "end": 292
		  },
		  "start": 290,
		  "end": 292,
		  "display": false
	  }, 
	  ...
	 ]
    }]

### 6.3.1 URL
    get3dPdb
### 6.3.2 参数
    uniprotId: 'PTEN_HUMAN',
    uniprotIds: 'PTEN_HUMAN',
### 6.3.3 成功时返回
    [
        {
        	"alignmentId": 3631206,
        	"pdbId": "3v0g",
        	"pdbTo": "278",
        	"chain": "B",
        	"alignmentString": "M A  +  +S+NKRRY++DGFDLDLTY+  ++IAM FP+",
        	"uniprotFrom": 1,
        	"uniprotId": "PTEN_HUMAN",
        	"pdbFrom": "240",
        	"uniprotTo": 39,
        	"eValue": 0,
        	"identityPerc": 56.4103
        }, 
        {
        	"alignmentId": 3631191,
        	"pdbId": "3v0d",
        	"pdbTo": "278",
        	"chain": "B",
        	"alignmentString": "+S+NKRRY++DGFDLDLTY+  ++IAM FP+",
        	"uniprotFrom": 9,
        	"uniprotId": "PTEN_HUMAN",
        	"pdbFrom": "248",
        	"uniprotTo": 39,
        	"eValue": 0,
        	"identityPerc": 64.5161
        }, 
        ...
    ]

### 6.4.1 URL
    get3dPdb
### 6.4.2 参数
    uniprotId: 'PTEN_HUMAN',
    uniprotIds: 'PTEN_HUMAN',
    type: 'summary',
### 6.4.3 成功时返回
    {alignmentCount: 31}

### 6.5.1 URL
    get3dPdb
### 6.5.2 参数
    pdbIds: '1d5r,2kyl,4o1v,3v0g,3v0d,3v0g,3v0f,3v0h,3v0g,3v0g,3v0h,3v0d,3v0f,3v0j,3v0j,3awf,3awe,3awf,3awe,3awg,3awg,3awg,3v0e,3awe,3awf'
### 6.5.3 成功时返回
    {
        "1d5r": {
            "source": {
                "1": {
                    "expression_system_cell_line": "high five",
                    "expression_system_vector": "baculovirus",
                    "organism_scientific": "homo sapiens",
                    "organism_common": "human",
                    "organism_taxid": "9606",
                    "expression_system_common": "cabbage looper",
                    "expression_system_taxid": "7111",
                    "expression_system": "trichoplusia ni",
                    "mol_id": "1",
                }
            },
            "title": "crystal structure of the pten tumor suppressor",
            "compound": {
                "1": {
                    "engineered": "yes",
                    "chain": ["a"],
                    "fragment": "residues 7-353",
                    "molecule": "phosphoinositide phosphatase pten",
                    "ec": "3.1.3.48",
                    "mol_id": "1",
                }
            }
        },
        "2kyl": {
            "source": {
                "1": {
                    "expression_system_vector": "pdest15",
                    "organism_scientific": "homo sapiens",
                    "organism_common": "human",
                    "expression_system_vector_type": "vector",
                    "organism_taxid": "9606",
                    "expression_system_taxid": "562",
                    "expression_system": "escherichia coli",
                    "mol_id": "1",
                },
                "2": {
                    "synthetic": "yes",
                    "mol_id": "2",
                }
            },
            "title": "solution structure of mast2-pdz complexed with the c-terminus of pten",
            "compound": {
                "1": {
                    "engineered": "yes",
                    "chain": ["a"],
                    "fragment": "pdz domain",
                    "molecule": "microtubule-associated serine/threonine-protein kinase 2",
                    "ec": "2.7.11.1",
                    "mol_id": "1",
                },
                "2": {
                    "synonym": "c-terminus of pten",
                    "chain": ["b"],
                    "molecule": "c-terminus of phosphatidylinositol-3,4,5-trisphosphate 3- phosphatase and dual-specificity protein phosphatase pten",
                    "mol_id": "2",
                }
            }
        },
        ...
    }

### 6.6.1 URL
    get3dPdb
### 6.6.2 参数
    positions: 65,78,154,171
    alignments: 3631102,3631104,3631105,3631103,3631106,3631107,3631101
### 6.6.3 成功时返回
    {
        65: {
            pdbPos: 65
        }, 
        78: {
            pdbPos: 78
        }, 
        154: {
            pdbPos: 154
        }, 
        171: {
            pdbPos: 171
        }
    }
### 6.7.1 URL
    designPrimerBySnv
### 6.7.2 参数
    snv: 10:89623861:T:-
### 6.7.3 成功时返回
    {
        "msg": "success",
        "code": 0,
        "message": "success",
        "content": {
            "data": [
                {
                    "left primer": ["357", "20", "59.10", "55.00", "0.00", "0.00", "0.00", "TCCTCGGCTTCTCCTGAAAG"],
                    "stats": "PRODUCT SIZE: 583, PAIR ANY_TH COMPL: 14.30, PAIR 3'_TH COMPL: 5.87",
                    "right primer": ["939", "20", "59.07", "55.00", "0.00", "0.00", "0.00", "AGGAGGAGAGAGATGGCAGA"],
                },
                {
                    "left primer": ["320", "20", "59.03", "50.00", "0.00", "0.00", "0.00", "TCGCCTCCTCTTCGTCTTTT"],
                    "stats": "PRODUCT SIZE: 567, PAIR ANY_TH COMPL: 0.00, PAIR 3'_TH COMPL: 0.00",
                    "right primer": ["886", "20", "59.19", "55.00", "0.00", "0.00", "0.00", "GAAATGGCTCTGGACTTGGC"]
                },
                ...
            ],
            "header": ["start", "len", "tm", "gc%", "any_th", "3'_th", "hairpin", "seq"]
        }
    }

### 七、PathwayComparator app
![image](https://github.com/wwlOath/MarkDownPhotos/blob/master/16.png?raw=true)

### 1、PathwayComparator
![image](https://github.com/wwlOath/MarkDownPhotos/blob/master/17.png?raw=true)
