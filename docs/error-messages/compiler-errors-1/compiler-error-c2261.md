---
title: "Erreur du compilateur C2261 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2261"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2261"
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2261
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'chaîne' : la référence d'assembly n'est pas valide et ne peut pas être résolue  
  
 Une valeur n'était pas valide.  
  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> est utilisé pour spécifier un assembly friend.  Par exemple, si a.dll souhaite spécifier b.dll comme assembly friend, vous devez spécifier \(dans a.dll\) : InternalsVisibleTo\("b"\).  Le runtime permet ensuite à b.dll d'accéder à tout le contenu d'a.dll \(sauf aux types privés\).  
  
 Pour plus d'informations sur la syntaxe correcte à utiliser lors de la spécification des assemblys friend, consultez [Assemblys friend \(C\+\+\)](../../dotnet/friend-assemblies-cpp.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C2261 :  
  
```  
// C2261.cpp  
// compile with: /clr /c  
using namespace System::Runtime::CompilerServices;  
[assembly: InternalsVisibleTo("a,a,a")];   // C2261  
[assembly: InternalsVisibleTo("a.a")];   // OK  
[assembly: InternalsVisibleTo("a")];   // OK  
```