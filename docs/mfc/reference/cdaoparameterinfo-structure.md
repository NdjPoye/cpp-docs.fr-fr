---
title: "CDaoParameterInfo, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoParameterInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoParameterInfo (structure)"
  - "DAO (Data Access Objects), Parameters (collection)"
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# CDaoParameterInfo, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `CDaoParameterInfo` contient des informations sur un objet paramètre défini pour les objets d'accès aux données \(DAO\).  
  
## Syntaxe  
  
```  
  
      struct CDaoParameterInfo  
{  
   CString m_strName;       // Primary  
   short m_nType;           // Primary  
   ColeVariant m_varValue;  // Secondary  
};  
```  
  
#### Paramètres  
 `m_strName`  
 Nomme de façon unique l'objet de paramètre.  Pour plus d'informations, consultez le sujet "Propriété du nom" dans l'aide DAO.  
  
 `m_nType`  
 Valeur qui indique le type de données d'un objet de paramètre.  Pour obtenir la liste des valeurs possibles, consultez le membre `m_nType` de la structure [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md).  Pour plus d'informations, consultez le sujet "Propriétés des types" dans l'aide DAO.  
  
 *m\_varValue*  
 La valeur du paramètre, stockée dans un objet [COleVariant](../../mfc/reference/colevariant-class.md).  
  
## Notes  
 Des références au primaire et au secondaire au dessus indiquent comment les informations sont retournées par la méthode [GetParameterInfo](../Topic/CDaoQueryDef::GetParameterInfo.md) de la classe `CDaoQueryDef`.  
  
 MFC n'encapsule pas les objets de paramètres DAO dans une classe.  Les objets de querydef de DAO sous\-jacents des objets MFC `CDaoQueryDef` stockent des paramètres dans leurs collections de paramètres.  Pour accéder aux objets de paramètre dans un objet [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md), appelez la méthode `GetParameterInfo` de l'objet de querydef pour un nom de paramètre spécifique ou un index dans la collection de paramètres.  Vous pouvez utiliser la méthode [CDaoQueryDef::GetParameterCount](../Topic/CDaoQueryDef::GetParameterCount.md) conjointement avec `GetParameterInfo` pour faire une boucle dans la collection de paramètres.  
  
 Les informations récupérées par la méthode [CDaoQueryDef::GetParameterInfo](../Topic/CDaoQueryDef::GetParameterInfo.md) sont stockées dans une structure `CDaoParameterInfo`.  Appelez `GetParameterInfo` pour l'objet querydef dont la collection de paramètres contient l'objet paramètre.  
  
> [!NOTE]
>  Si vous souhaitez obtenir ou définir uniquement la valeur d'un paramètre, utilisez les méthodes [GetParamValue](../Topic/CDaoRecordset::GetParamValue.md) et [SetParamValue](../Topic/CDaoRecordset::SetParamValue.md) de la classe `CDaoRecordset`.  
  
 `CDaoParameterInfo` définit également une méthode `Dump` dans les versions de débogage.  Vous pouvez utiliser `Dump` pour vider le contenu d'un objet `CDaoParameterInfo`.  
  
## Configuration requise  
 **En\-tête :** afxdao.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)