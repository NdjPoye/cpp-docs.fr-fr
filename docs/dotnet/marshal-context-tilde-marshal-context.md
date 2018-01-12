---
title: "marshal_context :: ~ marshal_context | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- marshal_context::~marshal_context
- msclr.interop.marshal_context.~marshal_context
- marshal_context.~marshal_context
- msclr::interop::marshal_context::~marshal_context
- ~marshal_context
dev_langs: C++
helpviewer_keywords: marshal_context class [C++], operations
ms.assetid: 34c41b38-4c33-4f61-b74e-831ac46b4ab5
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 42af11d58804a000e630d916cd5887c5005aa955
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="marshalcontextmarshalcontext"></a>marshal_context::~marshal_context
Détruit un objet `marshal_context`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
~marshal_context();  
```  
  
## <a name="remarks"></a>Notes  
 Certaines conversions de données nécessitent un contexte de marshaler. Consultez [vue d’ensemble du Marshaling dans C++](../dotnet/overview-of-marshaling-in-cpp.md) pour plus d’informations sur les traductions nécessitent un contexte et le marshaling du fichier doit être inclus dans votre application.  
  
 Suppression d’un `marshal_context` objet invalide les données converties par ce contexte. Si vous souhaitez conserver vos données après un `marshal_context` objet est détruit, vous devez copier manuellement les données à une variable qui est conservés.  
  
## <a name="requirements"></a>Configuration requise  
 **Fichier d’en-tête :** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, ou \<msclr\marshal_atl.h >  
  
 **Namespace :** msclr::interop  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble du Marshaling dans C++](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)   
 [marshal_context Class](../dotnet/marshal-context-class.md)