---
title: "/J (Type de caract&#232;re par d&#233;faut non sign&#233;) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned"
  - "VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned"
  - "/j"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/J (option du compilateur C++)"
  - "caractères (type de données)"
  - "type de caractère par défaut non signé"
  - "valeurs par défaut, caractères (type)"
  - "J (option du compilateur C++)"
  - "-J (option du compilateur C++)"
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# /J (Type de caract&#232;re par d&#233;faut non sign&#233;)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Remplace la valeur du type `char` par défaut en la faisant passer de `signed char` à `unsigned char`, et le type `char` est étendu avec un zéro lorsqu'il est élargi à un type `int`.  
  
## Syntaxe  
  
```  
/J  
```  
  
## Notes  
 Si une valeur `char` est déclarée explicitement comme étant `signed`, l'option **\/J** ne l'affecte pas, et la valeur est étendue par un signe lorsqu'elle est élargie à un type `int`.  
  
 L'option **\/J** définit `_CHAR_UNSIGNED`, qui est utilisé avec `#ifndef` dans le fichier LIMITS.h pour définir la plage du type `char` par défaut.  
  
 C et C\+\+ AINSI ne requièrent pas une implémentation spécifique du type `char`.  Cette option est utile lorsque vous utilisez des données caractères qui seront finalement converties dans une langue autre que l'anglais.  
  
> [!NOTE]
>  Si vous utilisez cette option du compilateur fourni avec ATL\/MFC, une erreur peut être générée.  Bien que vous pouvez désactiver cette erreur lorsque vous définissez `_ATL_ALLOW_CHAR_UNSIGNED`, cette solution n'est pas prise en charge et peut ne pas fonctionner.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Dans l'**Explorateur de solutions**, ouvrez le menu contextuel du projet et choisissez **Propriétés**.  
  
2.  Dans la boîte de dialogue **Pages de propriétés** du projet, dans le volet gauche sous **Propriétés de configuration**, développez **C\/C\+\+** puis sélectionnez **Ligne de commande**.  
  
3.  Dans le volet **Options supplémentaires**, spécifiez l'option du compilateur **\/J**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md)