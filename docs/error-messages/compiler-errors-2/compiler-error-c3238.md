---
title: Erreur du compilateur C3238 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3238
dev_langs: C++
helpviewer_keywords: C3238
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e729e0da83638c93dd7e79a55bc0960590f93f08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3238"></a>Erreur du compilateur C3238
'type' : un type portant ce nom a déjà été transféré à l’assembly 'assembly'  
  
 Un type a été défini dans une application cliente qui est aussi définie, via la syntaxe de transfert de type, dans un assembly référencé. Les deux types ne peuvent pas être définis dans l’étendue de l’application.  
  
 Consultez [transfert de Type (C + c++ / CLI)](../../windows/type-forwarding-cpp-cli.md) pour plus d’informations.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant crée un assembly qui contient un type qui a été transféré à partir d’un autre assembly.  
  
```  
// C3238.cpp  
// compile with: /clr /LD  
public ref class R {};  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant crée un assembly qui contenait la définition du type, mais qui ne contient maintenant que la syntaxe de transfert de type.  
  
```  
// C3238_b.cpp  
// compile with: /clr /LD  
#using "C3238.dll"  
[ assembly:TypeForwardedTo(R::typeid) ];  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3238 :  
  
```  
// C3238_c.cpp  
// compile with: /clr /c  
// C3238 expected  
// Delete the following line to resolve.  
#using "C3238_b.dll"  
public ref class R {};  
```