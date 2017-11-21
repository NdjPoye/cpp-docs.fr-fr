---
title: "Comment : déterminer l’état interactif des utilisateurs (C + c++ / CLI) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Visual C++, user interactive state
- user interactive state
ms.assetid: 9f52323e-38b8-4a41-9b1d-052012ad839b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f65933a1cbd81c0794263dfe3fa2628f52599257
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-determine-the-user-interactive-state-ccli"></a>Comment : déterminer l'état interactif d'un utilisateur (C++/CLI)
L’exemple de code suivant montre comment déterminer si le code est exécuté dans un contexte utilisateur interactif. Si <xref:System.Environment.UserInteractive%2A> est false, le code s’exécute comme un processus de service ou à partir d’à l’intérieur d’une application Web, auquel cas vous devez interagir avec l’utilisateur.  
  
## <a name="example"></a>Exemple  
  
```  
// user_interactive.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   if ( Environment::UserInteractive )  
      Console::WriteLine("User interactive");  
   else  
      Console::WriteLine("Noninteractive");  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Opérations Windows (C + c++ / CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [Programmation .NET avec C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)