---
title: "Initiation &#224; la migration de C++/CLI | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++/CLI Version 2"
  - "C++/CLI Version 2, extensions managées"
  - "extensions managées pour C++, mettre à niveau la syntaxe"
  - "migration (C++), C++/CLI Version 2"
  - "mettre à niveau les applications Visual C++, extensions managées pour C++ vers la syntaxe Visual C++ 2005"
ms.assetid: 8ec926b5-73f6-4f0c-bcdf-5203d293849a
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Initiation &#224; la migration de C++/CLI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ce document vous guidera pour porter vos programmes Visual C\+\+ d'Extensions managées pour C\+\+ sur [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  Pour une liste rapide des modifications syntaxiques, consultez [\(NOTINBUILD\)Managed Extensions for C\+\+ Syntax Upgrade Checklist](http://msdn.microsoft.com/fr-fr/edbded88-7ef3-4757-bd9d-b8f48ac2aada).  
  
 C\+\+\/CLI étend le paradigme de programmation par composants dynamiques au langage standard ISO\-C\+\+.  Le nouveau langage offre plusieurs améliorations significatives quant aux Extensions managées.  Ce document fournit une énumération des caractéristiques du langage des Extensions managées pour C\+\+ et de leur mappage à [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)], lorsqu'un tel mappage existe. Il signale également les constructions pour lesquelles aucun mappage n'existe.  
  
## Dans cette section  
 [Plan des modifications \(C\+\+\/CLI\)](../dotnet/outline-of-changes-cpp-cli.md)  
 Un survol pour référence rapide, qui fournit une liste des modifications classées en cinq grandes catégories.  
  
 [Mots clés de langage \(C\+\+\/CLI\)](../dotnet/language-keywords-cpp-cli.md)  
 Traite des modifications des mots\-clés du langage, en particulier de la suppression du trait de soulignement double et de l'introduction de mots clés à la fois contextuels et espacés.  
  
 [Types managés \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)  
 Examine les modifications syntaxiques apportées à la déclaration du système de type commun \(CTS, Common Type System\), soit les modifications de la déclaration de classes, de tableaux \(y compris le tableau de paramètres\), d'enums, etc.  
  
 [Déclarations de membre dans une classe ou interface \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)  
 Présente les modifications qui concernent des membres de classe tels que les propriétés scalaires, les propriétés d'index, les opérateurs, les délégués ou les événements.  
  
 [Types valeur et leurs comportements \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)  
 Se penche sur les types valeur et la nouvelle famille de pointeurs intérieurs et épingles.  Il expose également plusieurs modifications sémantiques significatives telles que l'introduction de la conversion boxing implicite, l'immuabilité de types valeur boxed et la suppression de la prise en charge des constructeurs par défaut dans les classes value.  
  
 [Modification d'ordre général apportée au langage](../dotnet/general-language-changes-cpp-cli.md)  
 Détaille des modifications sémantiques telles que la prise en charge de la notation de cast, le comportement des littéraux de chaîne et les modifications sémantiques entre ISO C\+\+ et C\+\+\/CLI.  
  
## Voir aussi  
 [Assemblys mixtes \(natif et managé\)](../dotnet/mixed-native-and-managed-assemblies.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)