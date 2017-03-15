---
title: "R&#232;gles de coh&#233;rence pour /Yc et /Yu | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/yc"
  - "/yu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Yc (option du compilateur C++)"
  - "/Yu (option du compilateur C++)"
  - "Yc (option du compilateur C++)"
  - "-Yc (option du compilateur C++)"
  - "Yu (option du compilateur C++)"
  - "-Yu (option du compilateur C++)"
ms.assetid: 9dfb0e32-ec9b-4a36-9355-27a0e5fba512
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# R&#232;gles de coh&#233;rence pour /Yc et /Yu
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lorsque vous utilisez un en\-tête précompilé créé à l'aide de l'option \/Yc ou \/Yu, le compilateur compare l'environnement de compilation en cours à celui en vigueur lors de la création du fichier .pch.  Veillez à spécifier un environnement cohérent avec le précédent \(cohérence des options de compilation, des pragmas, etc.\) pour la compilation en cours.  Si le compilateur détecte une incohérence, il émet un avertissement et identifie l'incohérence quand c'est possible.  De tels avertissements n'indiquent pas nécessairement un problème au niveau du fichier .pch ; ils signalent simplement des conflits éventuels.  Les sections suivantes passent en revue les critères requis pour la cohérence des en\-têtes précompilés.  
  
## Cohérence des options de compilation  
 Le tableau suivant répertorie les options de compilation pouvant déclencher un avertissement d'incohérence lors de l'utilisation d'un en\-tête précompilé.  
  
|Option|Nom|Règle|  
|------------|---------|-----------|  
|\/D|Définir des constantes et des macros|Doit rester identique entre la compilation qui a créé l'en\-tête précompilé et la compilation en cours.  L'état des constantes définies n'étant pas vérifié, des résultats imprévisibles peuvent apparaître si vos fichiers dépendent des valeurs des constantes modifiées.|  
|\/E ou \/EP|Copier la sortie du préprocesseur vers une sortie standard|Les en\-têtes précompilés ne fonctionnent pas avec l'option \/E ou \/EP.|  
|\/Fr ou \/FR|Générer des informations du navigateur source Microsoft|Pour que les options \/Fr et \/FR soient valides avec l'option \/Yu, elles doivent également avoir été activées lors de la création de l'en\-tête précompilé.  Les compilations ultérieures utilisant l'en\-tête précompilé génèrent également des informations du navigateur source.  Les informations du navigateur sont placées dans un seul fichier .sbr et sont référencées de la même manière que les informations CodeView.  Vous ne pouvez pas substituer le placement des informations du navigateur source.|  
|\/GA, \/GD, \/GE, \/Gw ou \/GW|Options de protocole Windows|Doit rester identique entre la compilation qui a créé l'en\-tête précompilé et la compilation en cours.  Si ces options diffèrent, un message d'avertissement apparaît.|  
|\/Zi|Générer des informations de débogage complètes|Si cette option est activée au moment où l'en\-tête précompilé est créé, les compilations ultérieures utilisant la précompilation peuvent exploiter les informations de débogage.  Si \/Zi n'est pas activée lors de la création de l'en\-tête précompilé, les compilations ultérieures utilisant la précompilation et l'option \/Zi émettent un avertissement.  Les informations de débogage sont placées dans le fichier objet en cours, et les symboles locaux définis dans l'en\-tête précompilé ne sont pas disponibles pour le débogueur.|  
  
> [!NOTE]
>  La fonctionnalité en\-têtes précompilés est destinée à être utilisée uniquement avec un fichier associé à des fichiers source C et C\+\+.  
  
## Cohérence du chemin d'accès Include  
 Un en\-tête précompilé créé à l'aide de l'option \/Yc ne contient pas d'informations sur le chemin d'accès include en vigueur lors de la création du fichier .pch.  Quand vous avez recours à un fichier .pch, le compilateur utilise toujours le chemin d'accès include spécifié dans la compilation en cours.  
  
## Cohérence du fichier source  
 Quand vous utilisez un en\-tête précompilé, le compilateur ignore toutes les directives du préprocesseur \(y compris les pragmas\) qui apparaissent avant le pragma hdrstop.  La compilation spécifiée par ces directives du préprocesseur doit être identique à celle qui est utilisée pour créer le fichier d'en\-tête précompilé.  
  
## Cohérence des pragmas  
 Les pragmas traités pendant la compilation d'un en\-tête précompilé affectent généralement le fichier dans lequel l'en\-tête précompilé est utilisé ultérieurement.  Les pragmas suivants affectent uniquement le code contenu dans le fichier .pch ; ils n'affectent pas le code qui utilise ultérieurement le fichier .pch :  
  
||||  
|-|-|-|  
|Commentaire|page|subtitle|  
|Linesize|pagesize|Titre|  
|Message|skip||  
  
 Les pragmas suivants sont conservés en tant qu'éléments constitutifs d'un en\-tête précompilé ; ils affectent le reste d'une compilation utilisant l'en\-tête précompilé :  
  
||||  
|-|-|-|  
|alloc\_text|function|optimize|  
|auto\_inline|inline\_depth|Pack|  
|check\_pointer|inline\_recursion|same\_seg|  
|check\_stack|intrinsic|warning|  
|code\_seg|loop\_opt||  
|data\_seg|native\_caller||  
  
## Voir aussi  
 [Règles de cohérence s'appliquant aux en\-têtes précompilés](../../build/reference/precompiled-header-consistency-rules.md)   
 [\/Yc \(Créer un fichier d'en\-tête précompilé\)](../../build/reference/yc-create-precompiled-header-file.md)   
 [\/Yu \(Utiliser un fichier d'en\-tête précompilé\)](../../build/reference/yu-use-precompiled-header-file.md)