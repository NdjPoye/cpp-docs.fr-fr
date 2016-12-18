---
title: "Mots cl&#233; d&#39;h&#233;ritage | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__multiple_inheritance"
  - "__single_inheritance_cpp"
  - "__virtual_inheritance_cpp"
  - "__virtual_inheritance"
  - "__multiple_inheritance_cpp"
  - "__single_inheritance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__multiple_inheritance (mot clé) (C++)"
  - "__single_inheritance (mot clé) (C++)"
  - "__virtual_inheritance (mot clé) (C++)"
  - "déclarer des classes dérivées"
  - "classes dérivées, déclarer"
  - "héritage, déclarer des classes dérivées"
  - "héritage, mots clés"
  - "mots clés (C++), mots clé d'héritage"
ms.assetid: bb810f56-7720-4fea-b8b6-9499edd141df
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mots cl&#233; d&#39;h&#233;ritage
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
```  
  
class [__single_inheritance] class-name; class [__multiple_inheritance] class-name; class [__virtual_inheritance] class-name;  
```  
  
 où :  
  
 *class\-name*  
 est le nom de la variable en cours de déclaration.  
  
 C\+\+ vous permet de déclarer un pointeur vers un membre de classe avant la définition de la classe.  Par exemple :  
  
```  
class S;  
int S::*p;  
```  
  
 Dans le code ci\-dessus, `p` est déclaré comme étant un pointeur vers membre entier de la classe S.  Toutefois, `class S` n'a pas encore été défini dans ce code ; il a uniquement été déclaré.  Lorsque le compilateur détecte ce type de pointeur, il doit créer une représentation généralisée du pointeur.  La taille de la représentation dépend du modèle d'héritage spécifié.  Il existe quatre façons de spécifier un modèle d'héritage au compilateur :  
  
-   Dans l'IDE, sous **Représentation d'un pointeur vers membre**  
  
-   En utilisant le commutateur [\/vmg](../build/reference/vmb-vmg-representation-method.md) sur la ligne de commande  
  
-   En utilisant le pragma [pointers\_to\_members](../preprocessor/pointers-to-members.md)  
  
-   En utilisant des mots clés d'héritage `__single_inheritance`, `__multiple_inheritance` et `__virtual_inheritance`.  Cette technique contrôle le modèle d'héritage pour chaque classe.  
  
    > [!NOTE]
    >  Si vous déclarez toujours un pointeur vers un membre d'une classe après la définition de la classe, vous n'avez pas besoin d'utiliser l'une de ces options.  
  
 La déclaration d'un pointeur vers un membre d'une classe avant la définition de classe a une incidence sur la taille et la vitesse du fichier exécutable résultant.  Plus l'héritage utilisé par une classe est complexe, plus le nombre d'octets requis pour représenter un pointeur vers un membre de la classe est élevé et plus le code nécessaire pour interpréter le pointeur est volumineux.  L'héritage unique est moins complexe, et l'héritage virtuel est plus complexe.  
  
 Si l'exemple ci\-dessus est modifié comme suit :  
  
```  
class __single_inheritance S;  
int S::*p;  
```  
  
 indépendamment des options de ligne de commande ou des pragmas, les pointeurs vers des membres de `class S` utiliseront la plus petite représentation possible.  
  
> [!NOTE]
>  La même déclaration anticipée d'une représentation de pointeur de classe vers membre devrait se produire dans chaque unité de traduction qui déclare des pointeurs vers des membres de cette classe, et la déclaration devrait se produire avant que les pointeurs vers des membres soient déclarées.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)