---
title: "/link (Passer des options &#224; l&#39;&#201;diteur de liens) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/link (option du compilateur C++)"
  - "cl.exe (compilateur C++), passer des options à l'éditeur de liens"
  - "link (option du compilateur C++)"
  - "-link (option du compilateur C++)"
  - "éditeur de liens (C++), passer des options à"
  - "passer des options à l'éditeur de liens"
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /link (Passer des options &#224; l&#39;&#201;diteur de liens)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Passe une ou plusieurs options de l'éditeur de liens à l'éditeur de liens.  
  
## Syntaxe  
  
```  
/link linkeroptions  
```  
  
## Arguments  
 `linkeroptions`  
 Options de l'éditeur de liens à passer à l'éditeur de liens.  
  
## Notes  
 L'option **\/link** et ses options de l'éditeur de liens doivent apparaître après les noms de fichiers et les options CL éventuels.  Un espace est requis entre **\/link** et `linkeroptions`.  Pour plus d'informations, consultez [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur une page de propriétés de l'éditeur de liens.  
  
4.  Modifiez une ou plusieurs propriétés.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Cette option du compilateur ne peut pas être modifiée par programme.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)