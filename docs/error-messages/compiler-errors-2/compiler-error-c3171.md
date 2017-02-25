---
title: "Erreur du compilateur C3171 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3171"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3171"
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C3171
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'module' : impossible de spécifier des attributs de modèle différents dans un projet  
  
 Des attributs [module](../../windows/module-cpp.md) ayant des listes de paramètres différentes ont été trouvés dans deux des fichiers d'une compilation.  Un seul attribut `module` peut être spécifié pour chaque compilation.  
  
 Des attributs `module` identiques peuvent être spécifiés dans plusieurs fichiers de code source.  
  
 Par exemple, si les attributs `module` suivants ont été trouvés :  
  
```  
// C3171.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];  
int main() {}  
```  
  
 Ensuite,  
  
```  
// C3171b.cpp  
// compile with: C3171.cpp  
// C3171 expected  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];  
```  
  
 le compilateur génère l'erreur C3171 \(notez que les valeurs de version sont différentes\).