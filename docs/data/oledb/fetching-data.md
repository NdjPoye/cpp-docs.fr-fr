---
title: "Extraction de donn&#233;es | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "données (C++), extraction"
  - "extraction"
  - "OLE DB (modèles du consommateur) (C++), récupérer les données"
  - "jeux de lignes (C++), extraction"
ms.assetid: b07f747f-9855-4f27-a03d-b1d5b10fa284
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Extraction de donn&#233;es
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Après avoir ouvert les objets source de données, session et jeu de lignes, vous pouvez extraire les données.  Selon le type d'accesseur que vous utilisez, vous devrez peut\-être lier les colonnes.  
  
### Pour extraire des données  
  
1.  Ouvrez le jeu de lignes en utilisant la commande **Ouvrir** appropriée.  
  
2.  Si vous utilisez `CManualAccessor`, liez les colonnes de sortie, si ce n'est déjà fait.  Pour lier les colonnes, appelez `GetColumnInfo`, puis créez un accesseur avec les liaisons, comme illustré dans l'exemple suivant :  
  
    ```  
    // From the DBViewer Sample CDBTreeView::OnQueryEdit  
    // Get the column information  
    ULONG ulColumns       = 0;  
    DBCOLUMNINFO* pColumnInfo  = NULL;  
    LPOLESTR pStrings      = NULL;  
    if (rs.GetColumnInfo(&ulColumns, &pColumnInfo, &pStrings) != S_OK)  
        ThrowMyOLEDBException(rs.m_pRowset, IID_IColumnsInfo);  
    struct MYBIND* pBind = new MYBIND[ulColumns];  
    rs.CreateAccessor(ulColumns, &pBind[0], sizeof(MYBIND)*ulColumns);  
    for (ULONG l=0; l<ulColumns; l++)  
    rs.AddBindEntry(l+1, DBTYPE_STR, sizeof(TCHAR)*40, &pBind[l].szValue, NULL, &pBind[l].dwStatus);  
    rs.Bind();  
    ```  
  
3.  Écrivez une boucle `while` pour récupérer les données.  Dans la boucle, appelez `MoveNext` pour déplacer le curseur et comparez la valeur de retour à S\_OK, comme le montre l'exemple suivant :  
  
    ```  
    while (rs.MoveNext() == S_OK)  
    {  
        // Add code to fetch data here  
        // If you are not using an auto accessor, call rs.GetData()  
    }  
    ```  
  
4.  Dans la boucle `while`, vous pouvez extraire les données en fonction du type d'accesseur.  
  
    -   Si vous utilisez la classe [CAccessor](../../data/oledb/caccessor-class.md), vous devez avoir un enregistrement utilisateur qui contient des données membres.  Vous pouvez accéder aux données en utilisant ces données membres, comme indiqué dans l'exemple suivant :  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members directly. In this case, m_nFooID  
            // is declared in a user record that derives from  
            // CAccessor  
            wsprintf_s("%d", rs.m_nFooID);   
        }  
        ```  
  
    -   Si vous utilisez la classe `CDynamicAccessor` ou `CDynamicParameterAccessor`, vous pouvez extraire les données en utilisant les fonctions d'accès `GetValue` et `GetColumn`, comme le montre l'exemple suivant.  Si vous voulez déterminer le type de données que vous utilisez, faites appel à `GetType`.  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the dynamic accessor functions to retrieve your data.  
  
            ULONG ulColumns = rs.GetColumnCount();  
            for (ULONG i=0; i<ulColumns; i++)  
            {  
                rs.GetValue(i);  
            }  
        }  
        ```  
  
    -   Si vous utilisez `CManualAccessor`, vous devez spécifier vos propres données membres, les lier vous\-même et y accéder directement, comme indiqué dans l'exemple suivant :  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members you specified in the calls to  
            // AddBindEntry.  
  
            wsprintf_s("%s", szFoo);  
        }  
        ```  
  
## Voir aussi  
 [Utilisation des modèles du consommateur OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)