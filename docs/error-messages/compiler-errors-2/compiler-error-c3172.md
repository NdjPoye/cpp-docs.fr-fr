---
title: "Erreur du compilateur C3172 | Microsoft Docs"
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
  - "C3172"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3172"
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3172
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'nom\_module' : impossible de spécifier des attributs idl\_module différents dans un projet  
  
 Des attributs [idl\_module](../../windows/idl-module.md) ayant le même nom, mais des paramètres `dllname` ou `version`différents ont été trouvés dans deux des fichiers d'une compilation.  Un seul attribut `idl_module` peut être spécifié pour chaque compilation.  
  
 Des attributs `idl_module` identiques peuvent être spécifiés dans plusieurs fichiers de code source.  
  
 Par exemple, si les attributs `idl_module` suivants ont été trouvés :  
  
```  
// C3172.cpp  
[module(name="MyMod")];  
[ idl_module(name="x", dllname="file.dll", version="1.1") ];  
int main() {}  
```  
  
 Ensuite,  
  
```  
// C3172b.cpp  
// compile with: C3172.cpp  
// C3172 expected  
[ idl_module(name="x", dllname="file.dll", version="1.0") ];  
```  
  
 le compilateur génère l'erreur C3172 \(notez que les valeurs de version sont différentes\).