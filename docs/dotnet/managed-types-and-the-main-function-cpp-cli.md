---
title: "Types manag&#233;s et la fonction principale (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "main (fonction), dans les applications managées"
  - "code managé, main() (fonction)"
ms.assetid: 9d0e9620-58c4-4dac-a0e1-ffeb95f80fa5
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Types manag&#233;s et la fonction principale (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lors de l'écriture d'une application à l'aide de **\/clr**, les arguments de la fonction **main\(\)** ne peuvent pas être de type managé.  
  
 Exemple de signature appropriée :  
  
```  
// managed_types_and_main.cpp  
// compile with: /clr  
int main(int, char*[], char*[]) {}  
```  
  
## Voir aussi  
 [Types managés](../dotnet/managed-types-cpp-cli.md)