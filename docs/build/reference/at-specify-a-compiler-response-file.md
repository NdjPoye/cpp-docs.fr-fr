---
title: "@ (Sp&#233;cifier un fichier r&#233;ponse du compilateur) | Microsoft Docs"
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
  - "@"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "@ (option du compilateur)"
  - "compilateur cl.exe, spécifier des fichiers réponse"
  - "fichiers réponse, compilateur C/C++"
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# @ (Sp&#233;cifier un fichier r&#233;ponse du compilateur)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie un fichier réponse du compilateur.  
  
## Syntaxe  
  
```  
@response_file  
```  
  
## Arguments  
 `response_file`  
 Fichier texte contenant des commandes de compilation.  
  
## Notes  
 Un fichier réponse peut contenir toutes les commandes que vous spécifiez sur la ligne de commande.  Cela peut être utile si les arguments de ligne de commande excèdent les 127 caractères.  
  
 Il n'est pas possible de spécifier l'option **@** dans un fichier réponse.  Autrement dit, un fichier réponse ne peut pas incorporer un autre fichier réponse.  
  
 À partir de la ligne de commande, vous pouvez spécifier autant d'options de fichier réponse \(par exemple, `@respfile.1 @respfile.2`\) que vous le souhaitez.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
-   Un fichier réponse ne peut pas être spécifié dans l'environnement de développement et doit l'être sur la ligne de commande.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Cette option du compilateur ne peut pas être modifiée par programme.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)