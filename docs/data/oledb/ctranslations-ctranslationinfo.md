---
title: CTranslations, CTranslationInfo | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- m_szCatalog
- m_szSourceCatalog
- m_szTargetSchema
- m_szTargetCatalog
- m_szTargetName
- CTranslationInfo
- m_szSourceName
- m_szSchema
- CTranslations
- m_szName
- m_szSourceSchema
dev_langs:
- C++
helpviewer_keywords:
- m_szSourceSchema
- m_szSourceCatalog
- m_szSchema
- m_szTargetName
- m_szSourceName
- CTranslations typedef class
- m_szCatalog
- m_szTargetCatalog
- m_szName
- CTranslationInfo parameter class
- m_szTargetSchema
ms.assetid: 19a64828-2d4c-42a0-8bfb-b010e334a9b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 95bcede95c8d5de4f2c0e529a16e06277ac3240d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="ctranslations-ctranslationinfo"></a>CTranslations, CTranslationInfo
Appelez la classe typedef **CTranslations** pour implémenter sa classe de paramètre **CTranslationInfo**.  
  
## <a name="remarks"></a>Notes  
 Consultez [Classes de jeu de lignes de schéma et Classes Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) pour plus d’informations sur l’utilisation de classes typedef.  
  
 Cette classe identifie les conversions de caractères définies dans le catalogue qui sont accessibles à un utilisateur donné.  
  
 Le tableau suivant répertorie les membres de données de la classe et les colonnes correspondantes de OLE DB. Consultez [ensemble de lignes de traductions](https://msdn.microsoft.com/en-us/library/ms725365.aspx) dans les *de référence du programmeur OLE DB* pour plus d’informations sur le schéma et les colonnes.  
  
|Données membres|Colonnes de OLE DB|  
|------------------|--------------------|  
|m_szCatalog|TRANSLATION_CATALOG|  
|m_szSchema|TRANSLATION_SCHEMA|  
|m_szName|TRANSLATION_NAME|  
|m_szSourceCatalog|SOURCE_CHARACTER_SET_CATALOG|  
|m_szSourceSchema|SOURCE_CHARACTER_SET_SCHEMA|  
|m_szSourceName|SOURCE_CHARACTER_SET_NAME|  
|m_szTargetCatalog|TARGET_CHARACTER_SET_CATALOG|  
|m_szTargetSchema|TARGET_CHARACTER_SET_SCHEMA|  
|m_szTargetName|TARGET_CHARACTER_SET_NAME|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbsch.h  
  
## <a name="see-also"></a>Voir aussi  
 [CatDB](../../visual-cpp-samples.md)   
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)