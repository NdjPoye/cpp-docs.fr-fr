---
title: "Sp&#233;cificateurs de substitution (extensions du composant C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "spécificateurs de substitution, Visual C++"
  - "override (spécificateurs)"
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Sp&#233;cificateurs de substitution (extensions du composant C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les *spécificateurs de substitution* modifient le comportement des types hérités et des membres de types hérités dans les types dérivés.  
  
## Tous les runtimes  
 **Notes**  
  
 Pour plus d'informations sur les spécificateurs de substitution, consultez :  
  
-   [abstract](../windows/abstract-cpp-component-extensions.md)  
  
-   [new \(nouvel emplacement dans vtable\)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
-   [override](../windows/override-cpp-component-extensions.md)  
  
-   [sealed](../windows/sealed-cpp-component-extensions.md)  
  
-   [Spécificateurs de substitution et compilations natives](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)  
  
 `abstract` et `sealed` sont également valides dans les déclarations de type, où ils ne se comportent pas comme des spécificateurs de substitution.  
  
 Pour plus d'informations sur la substitution explicite des fonctions de classe de base, consultez [Substitutions explicites](../windows/explicit-overrides-cpp-component-extensions.md).  
  
## Windows Runtime  
 \(Aucune note de cette fonctionnalité de langage ne s'applique qu'au Windows Runtime.\)  
  
### Conditions requises  
 Option du compilateur : **\/ZW**  
  
## Common Language Runtime  
 \(Aucune note de cette fonctionnalité de langage ne s'applique qu'au Common Language Runtime.\)  
  
### Conditions requises  
 Option du compilateur : **\/clr**  
  
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)