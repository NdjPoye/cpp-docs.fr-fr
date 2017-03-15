---
title: "Macros (C/C++) | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "préprocesseur"
  - "préprocesseur, macros"
  - "Visual C++, macros de préprocesseur"
ms.assetid: a7bfc5d4-2537-4fe0-bef0-70cec0b43388
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Macros (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le prétraitement développe des macros dans toutes les lignes qui sont pas des directives de préprocesseur \(lignes qui ne contiennent pas **\#** comme premier caractère autre qu'un espace blanc\) et dans les parties de certaines directives qui ne sont pas ignorées dans le cadre d'une compilation conditionnelle. Les directives de « compilation conditionnelle » vous permettent de supprimer la compilation des parties d'un fichier source en testant une expression constante ou un identificateur pour déterminer quels blocs de texte sont transmis au compilateur et quels blocs de texte sont supprimés du fichier source pendant le prétraitement.  
  
 La directive `#define` est généralement utilisée pour associer des identificateurs explicites à des constantes, à des mots clés, ainsi qu'à des instructions et des expressions couramment utilisées.  Les identificateurs qui représentent des constantes sont parfois appelés « constantes symboliques » ou « constantes manifestes ». Les identificateurs qui représentent des instructions ou des expressions sont appelés « macros ». Dans cette documentation relative aux préprocesseurs, seul le terme « macro » est utilisé.  
  
 Lorsque le nom de la macro est identifié dans le texte source du programme ou dans les arguments de certaines autres commandes de préprocesseur, il est traité comme un appel à cette macro.  Le nom de la macro est remplacé par une copie du corps de la macro.  Si la macro accepte des arguments, les arguments réels suivant le nom de la macro sont substitués aux paramètres formels dans le corps de la macro.  Le processus visant à remplacer un appel de macro par la copie traitée du corps est appelé « expansion » de l'appel de macro.  
  
 En pratique, il existe deux types de macro. Les macros de type objet ne prennent aucun argument, alors que les macros de type fonction peuvent être définies pour accepter des arguments afin de ressembler à des appels de fonction et se comporter comme tel.  Étant donné que les macros ne génèrent pas d'appels de fonction réels, vous pouvez parfois rendre l'exécution des programmes plus rapide en remplaçant les appels de fonction par des macros. \(En C\+\+, les fonctions inline sont souvent une méthode conseillée.\) Toutefois, les macros peuvent être source de problèmes si vous ne les définissez ou ne les utilisez pas avec précaution.  Vous devrez peut\-être utiliser des parenthèses dans les définitions de macros avec des arguments afin de conserver la priorité appropriée dans une expression.  En outre, il est possible que les macros ne gèrent pas correctement les expressions avec effets secondaires.  Pour plus d'informations, consultez l'exemple `getrandom` dans [La directive \#define](../preprocessor/hash-define-directive-c-cpp.md).  
  
 Une fois que vous avez défini une macro, vous ne pouvez pas la redéfinir avec une autre valeur sans supprimer préalablement la définition d'origine.  Toutefois, vous pouvez la redéfinir avec exactement la même définition.  Ainsi, la même définition peut apparaître plusieurs fois dans un programme.  
  
 La directive \#**undef** supprime la définition d'une macro.  Une fois que vous avez supprimé la définition, vous pouvez redéfinir la macro avec une autre valeur.  [La directive \#define](../preprocessor/hash-define-directive-c-cpp.md) et [la directive \#undef](../preprocessor/hash-undef-directive-c-cpp.md) décrivent les directives `#define` et `#undef`, respectivement.  
  
 Pour plus d'informations, consultez  
  
-   [Macros et C\+\+](../preprocessor/macros-and-cpp.md)  
  
-   [Macros Variadic](../preprocessor/variadic-macros.md)  
  
-   [Macros prédéfinies](../preprocessor/predefined-macros.md)  
  
## Voir aussi  
 [Référence du préprocesseur C\/C\+\+](../preprocessor/c-cpp-preprocessor-reference.md)