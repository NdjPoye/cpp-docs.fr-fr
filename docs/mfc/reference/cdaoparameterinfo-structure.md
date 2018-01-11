---
title: Cdaoparameterinfo, Structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDaoParameterInfo
dev_langs: C++
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3aabdb1dd59e1039f81d2ffe75c0d9e0770e43db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo, structure
Le `CDaoParameterInfo` structure contient des informations sur un objet de paramètre défini pour les objets d’accès aux données (DAO).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct CDaoParameterInfo  
{  
    CString m_strName;       // Primary  
    short m_nType;           // Primary  
    ColeVariant m_varValue;  // Secondary  
};  
```  
  
#### <a name="parameters"></a>Paramètres  
 `m_strName`  
 Identifie l’objet de paramètre. Pour plus d’informations, consultez la rubrique « Nom de propriété » dans l’aide de DAO.  
  
 `m_nType`  
 Une valeur qui indique le type de données d’un objet de paramètre. Pour obtenir la liste des valeurs possibles, consultez la `m_nType` membre de la [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) structure. Pour plus d’informations, consultez la rubrique « Propriété de Type » dans l’aide de DAO.  
  
 *m_varValue*  
 La valeur du paramètre, qui est stocké dans un [COleVariant](../../mfc/reference/colevariant-class.md) objet.  
  
## <a name="remarks"></a>Notes  
 Les références aux principaux et secondaires ci-dessus indiquent la façon dont les informations sont retournées par la [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) fonction membre dans la classe `CDaoQueryDef`.  
  
 MFC n’encapsule pas les objets de paramètre DAO dans une classe. Querydef DAO MFC sous-jacente des objets `CDaoQueryDef` objets stockent les paramètres dans leurs collections de paramètres. Pour accéder aux objets de paramètre dans un [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) d’objet, appelez l’objet querydef `GetParameterInfo` fonction membre pour un nom de paramètre spécifique ou un index dans la collection de paramètres. Vous pouvez utiliser la [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) fonction membre conjointement avec `GetParameterInfo` pour parcourir la collection de paramètres.  
  
 Les informations extraites par le [CDaoQueryDef::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) fonction membre est stockée dans un `CDaoParameterInfo` structure. Appelez `GetParameterInfo` pour l’objet querydef dans dont la collection de paramètres est stocké l’objet de paramètre.  
  
> [!NOTE]
>  Si vous souhaitez obtenir ou définir uniquement la valeur d’un paramètre, utilisez le [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) et [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) fonctions membres de classe `CDaoRecordset`.  
  
 `CDaoParameterInfo`définit également un `Dump` builds de la fonction membre en mode débogage. Vous pouvez utiliser `Dump` pour vider le contenu d’un `CDaoParameterInfo` objet.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** afxdao.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef, classe](../../mfc/reference/cdaoquerydef-class.md)
