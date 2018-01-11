---
title: CDynamicParameterAccessor::GetParam | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicParameterAccessor::GetParam
- ATL.CDynamicParameterAccessor.GetParam
- CDynamicParameterAccessor::GetParam<ctype>
- CDynamicParameterAccessor.GetParam
- GetParam
- ATL::CDynamicParameterAccessor::GetParam<ctype>
- ATL::CDynamicParameterAccessor::GetParam
dev_langs: C++
helpviewer_keywords: GetParam method
ms.assetid: 893a6bf8-7b55-4f6d-8a10-a43b13be7f56
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7cdd27cfdd173e556bb9d4c6fd27a9d801a7f8c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicparameteraccessorgetparam"></a>CDynamicParameterAccessor::GetParam
Récupère les données de chaîne pour un paramètre spécifique à partir de la mémoire tampon de paramètre.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      template < class ctype > bool GetParam(   
   DBORDINAL nParam,   
   ctype* pData    
) const throw( );  
template < class ctype > bool GetParam(   
   TCHAR* pParamName,   
   ctype* pData    
) const throw( );  
void* GetParam(   
   DBORDINAL nParam    
) const throw( );  
void* GetParam(   
   TCHAR* pParamName    
) const throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `ctype`  
 Un paramètre basé sur un modèle qui est le type de données.  
  
 `nParam`  
 [in] Le numéro de paramètre (offset à partir de 1). Le paramètre 0 est réservé pour les valeurs de retournés. Le paramètre est l’index du paramètre en fonction de son ordre dans le SQL ou d’un appel de procédure stockée. Consultez [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) pour obtenir un exemple.  
  
 `pParamName`  
 [in] Le nom du paramètre.  
  
 `pData`  
 [out] Pointeur vers la mémoire contenant les données extraites de la mémoire tampon.  
  
## <a name="return-value"></a>Valeur de retour  
 Pour les versions non, pointe vers la mémoire contenant les données récupérées à partir de la mémoire tampon. Pour les versions basées sur un modèle, retourne **true** en cas de réussite ou **false** en cas d’échec.  
  
 Utilisez `GetParam` pour récupérer des données de paramètre de chaîne à partir de la mémoire tampon. Utilisez [GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md) pour récupérer les données de paramètre de chaîne à partir de la mémoire tampon.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)