---
title: Erreur du compilateur C2261 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2261
dev_langs:
- C++
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3907a1d270de11af82462815ce87398e10c50513
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2261"></a>Erreur du compilateur C2261
'string' : référence d’assembly n’est pas valide et ne peut pas être résolue  
  
 Une valeur n’est pas valide.  
  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>est utilisé pour spécifier un assembly friend. Par exemple, si.dll souhaite spécifier b.dll comme assembly friend, vous devez spécifier (dans.dll) : InternalsVisibleTo("b"). Le runtime permet ensuite à b.dll accéder à tous les éléments de.dll (à l’exception des types privés).  
  
 Pour plus d’informations sur la syntaxe correcte lors de la spécification des assemblys friend, consultez [assemblys Friend (C++)](../../dotnet/friend-assemblies-cpp.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C2261.  
  
```  
// C2261.cpp  
// compile with: /clr /c  
using namespace System::Runtime::CompilerServices;  
[assembly: InternalsVisibleTo("a,a,a")];   // C2261  
[assembly: InternalsVisibleTo("a.a")];   // OK  
[assembly: InternalsVisibleTo("a")];   // OK  
```