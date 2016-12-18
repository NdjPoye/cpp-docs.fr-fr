---
title: "Erreur du compilateur C3170 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3170"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3170"
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3170
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'avoir des identificateurs de module différents dans un projet  
  
 Des attributs [module](../../windows/module-cpp.md) ayant des noms différents ont été trouvés dans deux des fichiers d'une compilation.  Un seul attribut `module` peut être spécifié pour chaque compilation.  
  
 Des attributs `module` identiques peuvent être spécifiés dans plusieurs fichiers de code source.  
  
 Par exemple, si les attributs module suivants étaient trouvés :  
  
```  
// C3170.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
int main() {}  
```  
  
 Ensuite,  
  
```  
// C3170b.cpp  
// compile with: C3170.cpp  
// C3170 expected  
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
```  
  
 le compilateur générerait C3170 \(notez les noms différents\).