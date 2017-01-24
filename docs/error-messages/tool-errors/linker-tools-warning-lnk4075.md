---
title: "Avertissement des outils &#201;diteur de liens LNK4075 | Microsoft Docs"
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
  - "LNK4075"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4075"
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement des outils &#201;diteur de liens LNK4075
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

option1' ignoré à cause de la spécification 'option2'  
  
 La deuxième option substitue la première.  
  
 Des options de l'éditeur de liens qui s'excluent mutuellement sont spécifiées.  Examinez vos options de l'éditeur de liens.  L'endroit auquel les options de l'éditeur de liens sont spécifiées dépend de la manière dont vous générez votre projet.  
  
-   Si vous procédez à la génération dans l'environnement de développement, recherchez votre projet dans les pages de propriétés de l'éditeur de liens et déterminez à quel endroit les deux options de l'éditeur de liens sont spécifiées.  Pour plus d'informations, consultez [Comment : spécifier des propriétés de projet avec des pages de propriétés](../../misc/how-to-specify-project-properties-with-property-pages.md).  
  
-   Si vous procédez à la génération au niveau de la ligne de commande, observez les options de l'éditeur de liens spécifiées à cet endroit.  
  
-   Si vous procédez à la génération avec des scripts de génération, parcourez vos scripts pour déterminer à quel endroit ces options de l'éditeur de liens sont spécifiées.  
  
 Lorsque vous avez détecté à quel endroit les options de l'éditeur de liens qui s'excluent mutuellement sont spécifiées, supprimez l'une de ces options.  
  
 Quelques exemples spécifiques :  
  
-   Si vous liez un module compilé avec **\/ZI** \(ce qui implique une option de l'éditeur de liens interne appelée \/EDITANDCONTINUE\) et un module compilé avec \/OPT:REF, \/OPT:ICF ou \/INCREMENTAL:NO \(ce qui n'implique aucun \/EDITANDCONTINUE\), l'erreur LNK4075 est générée.  Pour plus d'informations, consultez [\/Z7, \/Zi, \/ZI \(Format des informations de débogage\)](../../build/reference/z7-zi-zi-debug-information-format.md).