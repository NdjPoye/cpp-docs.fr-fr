---
title: UUID (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: uuid_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad4362b8e84d7ffb4bb090a4e513538cdb26ae25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="uuid-c"></a>uuid (C++)
**Section spécifique à Microsoft**  
  
 Le compilateur attache un GUID à une classe ou à une structure déclarée ou définie (définitions complètes d'objet COM uniquement) avec l'attribut `uuid`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
__declspec( uuid("  
ComObjectGUID  
") ) declarator  
```  
  
## <a name="remarks"></a>Notes  
 L'attribut `uuid` prend une chaîne comme argument. Cette chaîne de nom à un GUID au format normal de Registre avec ou sans le **{}** délimiteurs. Exemple :  
  
```  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;  
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;  
```  
  
 Cet attribut peut être appliqué dans une redéclaration. Cela permet de fournir les définitions des interfaces telles que les en-têtes système **IUnknown**et la redéclaration dans un autre en-tête (par exemple, COMDEF. H) pour fournir un GUID.  
  
 Le mot clé [__uuidof](../cpp/uuidof-operator.md) peuvent être appliquées pour récupérer le GUID constant attaché à un type défini par l’utilisateur.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [__declspec](../cpp/declspec.md)   
 [Mots clés](../cpp/keywords-cpp.md)