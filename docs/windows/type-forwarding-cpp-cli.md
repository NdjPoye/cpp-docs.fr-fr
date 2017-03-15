---
title: "Type Forwarding (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "type forwarding, Visual C++"
ms.assetid: ae730b69-0c27-41cc-84e1-3132783866ea
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Type Forwarding (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le *transfert de type* permet de déplacer un type d'un assembly \(assembly A\) dans un assembly \(assembly B\), tel qu'il ne soit pas nécessaire de recompiler les clients qui utilisent l'assembly A.  
  
## Toutes les plateformes  
 Cette fonctionnalité n'est pas prise en charge dans les délais d'exécution.  
  
## Windows Runtime  
 Cette fonctionnalité n'est pas prise en charge danq [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
### Conditions requises  
 Option du compilateur : **\/ZW**  
  
## Common Language Runtime  
 L'exemple de code suivant montre comment utiliser les types de transfer.  
  
### Syntaxe  
  
```  
#using "new.dll"  
[assembly:TypeForwardedTo(type::typeid)];  
```  
  
### Paramètres  
 `new`  
 L'assembly sur lequel vous déplacez la définition de type.  
  
 `type`  
 La définition du type que vous déplacez dans un assembly.  
  
### Remarques  
 Une fois qu'un composant \(assembly\) est fourni et est utilisée par les applications clientes, vous pouvez utiliser le transfert de type pour entrer un type de composant \(assembly\) dans un autre assembly, sont fournis le composant mis à jour \(et tous les assemblys supplémentaires requis\), et les applications clientes fonctionneront toujours sans être recompilées.  
  
 Le transfère de type ne marche que pour les composants référencés par les applications existantes.  Lors de la reconstruction d'une application, il doit y avoir des références d'assembly appropriées pour tous les types utilisés dans l'application.  
  
 Lors du transfer du type \(le type A\) d'un assembly, vous devez ajouter l'attribut `TypeForwardedTo` pour ce type, ainsi qu'une référence d'assembly.  L'assembly que vous référencez doit contenir l'une des opérations suivantes :  
  
-   La définition du type A.  
  
-   Un attribut `TypeForwardedTo` pour le type A, ainsi qu'une référence d'assembly.  
  
 Les exemples de types qui peuvent être transférés sont les suivantes :  
  
-   ref classes  
  
-   value classes  
  
-   enums  
  
-   interfaces  
  
 Vous ne pouvez pas transmettre des types suivants :  
  
-   Types génériques  
  
-   Types natifs  
  
-   Types imbriqués \(si vous souhaitez transférer un type imbriquée, vous devez transférer le type englobant\)  
  
 Vous pouvez transférer un type dans un assembly créé dans n'importe quel langage ciblant le CLR.  
  
 Par conséquent, si un fichier de code source utilisé pour créer l'unité A.dll contient une définition de type \(`ref class MyClass`\), et vous souhaitiez déplacer la définition de type à l'assembly B.dll, vous :  
  
1.  Déplacez la définition du type `MyClass` dans un fichier de code source utilisé pour générer B.dll.  
  
2.  Créez l'assembly B.dll  
  
3.  Supprimez la définition du type `MyClass` de code source utilisé pour générer A.dll, puis remplacez \-la par :  
  
    ```  
    #using "B.dll"  
    [assembly:TypeForwardedTo(MyClass::typeid)];  
    ```  
  
4.  Construisez l'assembly A.dll.  
  
5.  Utilisez A.dll sans recompilation des applications clientes.  
  
### Conditions requises  
 Option du compilateur : **\/clr**