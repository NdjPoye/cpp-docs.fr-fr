---
title: CDaoParameterInfo (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoParameterInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoParameterInfo structure
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b41d26b736ea9f84c53f71dbd71949f74fb8ae52
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo, structure
Le `CDaoParameterInfo` structure contient des informations sur un objet de paramètre définie pour les objets d’accès aux données (DAO).  
  
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
 Une valeur qui indique le type de données d’un objet parameter. Pour obtenir la liste des valeurs possibles, consultez la `m_nType` membre de la [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) structure. Pour plus d’informations, consultez la rubrique « Type Property » dans l’aide de DAO.  
  
 *m_varValue*  
 La valeur du paramètre, stockée dans un [COleVariant](../../mfc/reference/colevariant-class.md) objet.  
  
## <a name="remarks"></a>Remarques  
 Les références aux principaux et secondaires ci-dessus indiquent comment les informations sont renvoyées par le [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) fonction membre dans la classe `CDaoQueryDef`.  
  
 MFC n’encapsule pas les objets de paramètre DAO dans une classe. Querydef DAO MFC sous-jacente des objets `CDaoQueryDef` objets stockent les paramètres dans les collections de paramètres. Pour accéder aux objets paramètre dans un [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) de l’objet, appelez l’objet querydef `GetParameterInfo` fonction membre pour un nom de paramètre particulier ou un index dans la collection de paramètres. Vous pouvez utiliser la [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) fonction membre conjointement avec `GetParameterInfo` pour parcourir la collection de paramètres.  
  
 Les informations récupérées par le [CDaoQueryDef::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) fonction membre est stockée dans un `CDaoParameterInfo` structure. Appelez `GetParameterInfo` pour l’objet querydef dont collection Parameters de l’objet de paramètre est stocké.  
  
> [!NOTE]
>  Si vous souhaitez obtenir ou définir uniquement la valeur d’un paramètre, utilisez le [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) et [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) fonctions membres de classe `CDaoRecordset`.  
  
 `CDaoParameterInfo`définit également un `Dump` builds de la fonction membre en mode de débogage. Vous pouvez utiliser `Dump` pour vider le contenu d’un `CDaoParameterInfo` objet.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdao.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef (classe)](../../mfc/reference/cdaoquerydef-class.md)

