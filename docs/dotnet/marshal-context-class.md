---
title: marshal_context, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: marshal_context
dev_langs: C++
helpviewer_keywords: marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9b59dfa82563a0c115f521bb881411981a30efc9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="marshalcontext-class"></a>marshal_context, classe
Cette classe convertit les données entre les environnements natifs et managés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class marshal_context  
```  
  
## <a name="remarks"></a>Notes  
 Utilisez la `marshal_context` classe pour les conversions de données qui requièrent un contexte. Consultez [vue d’ensemble du Marshaling dans C++](../dotnet/overview-of-marshaling-in-cpp.md) pour plus d’informations sur les conversions nécessitent un contexte et le marshaling du fichier doit être inclus. Le résultat du marshaling lorsque vous utilisez un contexte est valide uniquement jusqu'à la `marshal_context` objet est détruit. Pour conserver votre résultat, vous devez copier les données.  
  
 Le même `marshal_context` peut être utilisé pour plusieurs conversions de données. Réutiliser le contexte de cette manière n’affecte pas les résultats des appels précédents de marshaling.  
  
## <a name="requirements"></a>Configuration requise  
 **Fichier d’en-tête :** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, ou \<msclr\marshal_atl.h >  
  
 **Namespace :** msclr::interop  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble du Marshaling dans C++](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)