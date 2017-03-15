---
title: "Syntaxe de la ligne de commande de l&#39;&#201;diteur de liens | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LINK (outil C++), syntaxe de la ligne de commande"
  - "éditeur de liens (C++), syntaxe"
  - "éditeur de liens (ligne de commande) (C++)"
ms.assetid: e2a31e17-77bd-4e74-9305-75b105b26539
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Syntaxe de la ligne de commande de l&#39;&#201;diteur de liens
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour exécuter LINK.EXE, utilisez la syntaxe de commande suivante :  
  
```  
LINK arguments  
```  
  
 Les `arguments` incluent les options ainsi que les noms de fichiers, et peuvent être spécifiés dans un ordre quelconque.  Les options sont traitées en premier, suivies des fichiers.  Utilisez des espaces ou des tabulations pour séparer les arguments.  
  
> [!NOTE]
>  Vous pouvez démarrer cet outil uniquement à partir de l'invite de commandes [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  Vous ne pouvez pas le démarrer à partir d'une invite de commandes système ou dans l'Explorateur Windows.  
  
 Sur la ligne de commande, une option est constituée d'un spécificateur d'option, qui peut être un tiret \(–\) ou une barre oblique \(\/\), suivis du nom de l'option.  Les noms des options ne peuvent pas être abrégés.  Certaines options acceptent un argument spécifié après le signe deux\-points \(:\).  Les espaces et les tabulations sont interdits dans une spécification d'option, sauf dans une chaîne mise entre guillemets au sein de l'option \/COMMENT.  Spécifiez les arguments numériques en notation décimale ou de langage C.  Les noms des options et leurs arguments \(mots clés ou noms de fichiers\) ne respectent pas la casse, contrairement aux identificateurs utilisés comme arguments.  
  
 Pour passer un fichier à l'éditeur de liens, spécifiez le nom de fichier sur la ligne de commande après la commande LINK.  Vous pouvez spécifier un chemin d'accès absolu ou relatif avec le nom de fichier ou utiliser des caractères génériques dans le nom de fichier.  Si vous omettez le point \(.\) et l'extension du nom de fichier, LINK suppose qu'il s'agit de .obj à des fins de recherche du fichier.  LINK n'utilise pas les extensions de nom de fichier ou leur absence pour faire des suppositions sur le contenu des fichiers ; il détermine le type de fichier en l'examinant, puis en le traitant en conséquence.  
  
 link.exe retourne la valeur zéro en cas de réussite \(aucune erreur\).  Sinon, l'éditeur de liens retourne le numéro de l'erreur qui a interrompu le lien.  Par exemple, si l'éditeur de liens génère LNK1104, l'éditeur de liens retourne 1104. Par conséquent, le plus petit numéro d'erreur retourné par l'éditeur de liens sur une erreur est 1000. Une valeur de retour de 128 représente soit un problème de configuration du système d'exploitation soit un problème de configuration d'un fichier .config; le chargeur n'a pas chargé soit link.exe soit c2.dll.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)