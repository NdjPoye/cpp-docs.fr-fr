---
title: "Mod&#232;les de classe | Microsoft Docs"
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
  - "modèles de classe"
  - "classes (C++), utiliser le type"
  - "modèles, modèles de classe"
ms.assetid: 633a53c8-24ee-4c23-8c88-e7c3cb0b7ac3
caps.latest.revision: 13
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mod&#232;les de classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser des modèles de classe pour créer une famille des classes qui fonctionnent avec un type.  Les modèles de classes sont des types paramétrables.  Ils impliquent qu'une classe distincte peut être créée pour chaque valeur possible des paramètres \(appelés arguments template\) passés.  
  
 Les arguments template peuvent être des types ou des valeurs de constante d'un type spécifié.  Par exemple :  
  
```  
// class_templates.cpp  
template <class T, int i> class TempClass   
{  
public:  
    TempClass( void );  
    ~TempClass( void );  
    int MemberSet( T a, int b );  
private:  
    T Tarray[i];  
    int arraysize;  
};  
  
int main()  
{  
}  
```  
  
 Dans cet exemple, la classe modélisée utilise deux paramètres, un type `T` et un int `i`.  N'importe quel type peut être passé au paramètre `T`, y compris les structures et les classes.  Une constante entière doit être passée au paramètre `i`.  Étant donné que `i` est une constante définie au moment de la compilation, vous pouvez définir un tableau de membres de taille `i` à l'aide d'une déclaration de tableau standard.  
  
 Pour plus d'informations, consultez :  
  
-   [Membres de modèles de classes](../Topic/Members%20of%20Class%20Templates.md)  
  
-   [Modèles pour les membres de classe](../Topic/Templates%20for%20Class%20Members.md)  
  
-   [Fonctions membres de classes de modèles](../Topic/Member%20Functions%20of%20Template%20Classes.md)  
  
-   [Modèles de classes imbriqués](../Topic/Nested%20Class%20Templates.md)  
  
-   [Instanciation de modèle de classe](../Topic/Class%20Template%20Instantiation.md)  
  
-   [Spécialisation explicite des modèles de classe](../Topic/Explicit%20Specialization%20of%20Class%20Templates.md)  
  
-   [Spécialisation partielle des modèles de classes](../cpp/template-specialization-cpp.md)  
  
-   [Arguments par défaut pour les modèles de classe](../Topic/Default%20Arguments%20for%20Class%20Templates.md)  
  
-   [Friends de modèle](../cpp/template-friends.md)  
  
## Voir aussi  
 [Modèles](../cpp/templates-cpp.md)