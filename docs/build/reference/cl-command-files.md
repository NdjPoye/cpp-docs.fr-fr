---
title: "Fichiers de commandes CL | Microsoft Docs"
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
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compilateur cl.exe, fichiers de commandes"
  - "fichiers de commandes"
  - "fichiers de commandes, CL (compilateur)"
ms.assetid: ec3cea06-2af0-4fe9-a94c-119c9d31b3a9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fichiers de commandes CL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un fichier de commandes est un fichier texte qui contient des options et des noms de fichiers que vous devez autrement entrer sur la [ligne de commande](../../build/reference/compiler-command-line-syntax.md) ou spécifier à l'aide de la [variable d'environnement CL](../../build/reference/cl-environment-variables.md).  CL accepte un fichier de commandes du compilateur en tant qu'argument dans la variable d'environnement CL ou sur la ligne de commande.  Contrairement à la ligne de commande et à la variable d'environnement CL, un fichier de commandes admet l'utilisation de plusieurs lignes d'options et de noms de fichiers.  
  
 Les options et les noms de fichiers qui figurent dans un fichier de commandes sont traités en fonction de l'emplacement qu'occupe un nom de fichier de commandes dans la variable d'environnement CL ou sur la ligne de commande.  Cependant, si l'option \/link apparaît dans le fichier de commandes, toutes les options qui figurent sur le reste de la ligne sont passées à l'éditeur de liens.  Les options des lignes suivantes du fichier de commandes et les options situées sur la ligne de commande après l'appel du fichier de commandes sont toujours acceptées en tant qu'options du compilateur.  Pour plus d'informations sur la façon dont l'ordre des options influe sur leur interprétation, consultez [Ordre des options CL](../../build/reference/order-of-cl-options.md).  
  
 Un fichier de commandes ne doit pas contenir la commande CL.  Chaque option doit commencer et se terminer sur la même ligne ; vous ne pouvez pas utiliser la barre oblique inverse \(\\\) pour combiner une option répartie sur deux lignes.  
  
 Un fichier de commandes est spécifié par le signe arobase\(@\) suivi d'un nom de fichier ; le nom de fichier peut spécifier un chemin d'accès absolu ou relatif.  
  
 Par exemple, si la commande suivante se trouve dans un fichier nommé RESP :  
  
```  
/Og /link LIBC.LIB  
```  
  
 et que vous spécifiez la commande CL suivante :  
  
```  
CL /Ob2 @RESP MYAPP.C  
```  
  
 la commande pour CL est comme suit :  
  
```  
CL /Ob2 /Og MYAPP.C /link LIBC.LIB  
```  
  
 Notez que les commandes de la ligne de commande et du fichier de commandes sont combinées efficacement.  
  
## Voir aussi  
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)