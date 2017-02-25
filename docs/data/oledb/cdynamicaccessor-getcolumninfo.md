---
title: "CDynamicAccessor::GetColumnInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetColumnInfo"
  - "ATL.CDynamicAccessor.GetColumnInfo"
  - "ATL::CDynamicAccessor::GetColumnInfo"
  - "CDynamicAccessor.GetColumnInfo"
  - "CDynamicAccessor::GetColumnInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetColumnInfo (méthode)"
ms.assetid: 7f2102ea-b7cc-4714-812f-3ca2857f4b9a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::GetColumnInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne les métadonnées de colonne exigées par la plupart des consommateurs.  
  
## Syntaxe  
  
```  
  
      HRESULT GetColumnInfo(   
   IRowset* pRowset,   
   DBORDINAL* pColumns,   
   DBCOLUMNINFO** ppColumnInfo,   
   OLECHAR** ppStringsBuffer    
) throw( );  
```  
  
#### Paramètres  
 `pRowset`  
 \[in\] Pointeur vers l'interface [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx)  
  
 *pColumns*  
 \[out\] Pointeur vers la mémoire dans lequel retourner le nombre de colonnes dans le jeu de lignes ; ce nombre inclut la colonne de signet, s'il y en a une.  
  
 *ppColumnInfo*  
 \[out\] Pointeur vers la mémoire dans lequel retourner un tableau de structures **DBCOLUMNINFO**.  Consultez « structure DBCOLUMNINFO » dans [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) dans le *guide de référence du programmeur OLE DB*.  
  
 `ppStringsBuffer`  
 \[out\] Pointeur vers la mémoire dans lequel retourner un pointeur pour stocker toutes les valeurs de chaîne \(noms utilisés dans *columnid* ou pour *pwszName*\) dans un bloc d'allocation unique.  
  
## Valeur de retour  
 Une des valeurs standard `HRESULT`.  
  
## Notes  
 Voir le [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) dans le *guide de référence du programmeur OLE DB* pour plus d'informations sur les types de données **DBORDINAL**, **DBCOLUMNINFO**, et **OLECHAR**.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)