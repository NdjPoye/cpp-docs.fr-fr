---
title: "partial (extensions de composant C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "partial_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "partial"
  - "C++/CX, partial"
ms.assetid: 43adf1f5-10c5-44aa-a66f-7507e2bdabf8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# partial (extensions de composant C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le mot clé `partial` permet à différentes parties de la même classe de référence d'être créées de manière indépendante et dans des fichiers différents.  
  
## Tous les runtimes  
 \(Cette fonctionnalité de langage s'applique uniquement à [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].\)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Pour une classe de référence possédant deux définitions partielles, le mot clé `partial` est appliqué à la première occurrence de la définition, en général via un code généré automatiquement, afin qu'un codeur humain n'utilise pas ce mot clé très souvent.  Pour toutes les définitions partielles suivantes de la classe, omettez le modificateur `partial` du mot clé *clé\-classe* et de l'identificateur de classe.  Lorsque le compilateur rencontre une classe de référence et un identificateur de classe définis précédemment mais aucun mot clé `partial`, il combine en interne toutes les parties de la définition de classe de référence en une seule définition.  
  
### Syntaxe  
  
```cpp  
  
partial class-key identifier {  
   /* The first part of the partial class definition. This is typically auto-generated*/  
}  
// ...  
class-key identifier {  
   /* The subsequent part(s) of the class definition. The same identifier is specified, but the "partial" keyword is omitted. */  
}  
  
```  
  
### Paramètres  
 *class\-key*  
 Mot clé qui déclare une classe ou une structure prises en charge par [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  `ref class`, `value class`, `ref struct` ou `value struct`.  
  
 *identifier*  
 Nom du type défini.  
  
### Remarques  
 Une classe partielle prend en charge les scénarios dans lesquels vous modifiez une partie d'une définition de classe dans un fichier. Un logiciel de génération de code automatique, par exemple le concepteur XAML, modifie le code de la même classe dans un autre fichier.  L'utilisation d'une classe partielle vous permet d'empêcher le générateur de code automatique de remplacer votre code.  Dans un projet Visual Studio, le modificateur `partial` est appliqué automatiquement au fichier généré.  
  
 Contenu : à deux exceptions près, une définition de classe partielle peut contenir tout ce que la définition de classe complète peut contenir si le mot clé `partial` a été omis.  Toutefois, vous ne pouvez pas spécifier l'accessibilité de classe \(par exemple, `public partial class X {…};`\), ou `declspec`.  
  
 Les spécificateurs d'accès utilisés dans une définition de classe partielle pour *identifier* n'affectent pas l'accessibilité par défaut dans une définition de classe partielle ou complète suivante pour identifier *identifier*.  Les définitions intégrées des données membres statiques sont autorisées.  
  
 Déclaration : la définition d'un *identifier* de classe présente uniquement le nom identificateur *identifier*, mais *identifier* ne peut pas être utilisé d'une manière qui nécessite une définition de classe.  Le nom *identifier* ne peut pas être utilisé pour connaître la taille de *identifier*, ou pour utiliser une base ou un membre *identifier* tant que le compilateur ne rencontre pas la définition complète de *identifier*.  
  
 Nombre et classement : il peut y avoir plusieurs définitions de classe partielle pour *identifier* ou aucune.  Chaque définition de classe partielle de *identifier* doit précéder de façon lexicale une définition complète de *identifier* \(s'il existe une définition complète ; sinon, la classe ne peut pas être utilisée, sauf si elle a été déclarée avant\), mais elle ne doit pas précéder les déclarations anticipées de *identifier*.  Toutes les clés de classe doivent correspondre.  
  
 Définition complète : dans la phase de définition complète de la classe *identifier*, le comportement est identique, comme si la définition de *identifier* avait déclaré toutes les classes de base, les membres, etc dans l'ordre dans lequel ils ont été rencontrés et définis dans les classes partielles.  
  
 Modèles : une classe partielle ne peut pas être un modèle.  
  
 Génériques : une classe partielle peut être un générique si la définition complète peut être générique.  Mais chaque classe partielle et complète doit avoir exactement les mêmes paramètres génériques, y compris les noms des paramètres formels.  
  
 Pour plus d'informations sur l'utilisation du mot clé `partial`, consultez [Classes partielles \(C\+\+\/CX\)](http://go.microsoft.com/fwlink/p/?LinkId=249023).  
  
### Conditions requises  
 Option du compilateur : **\/ZW**  
  
## Common Language Runtime  
 \(Cette fonctionnalité de langage ne s'applique pas au Common Language Runtime.\)  
  
## Voir aussi  
 [Classes partielles \(C\+\+\/CX\)](http://go.microsoft.com/fwlink/p/?LinkId=249023)