---
title: "Initialisation des tableaux | Microsoft Docs"
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
  - "initialiser des tableaux"
  - "tableaux (C++), l’initialisation"
ms.assetid: 41efe5f0-15b5-4f49-9196-c4902f8fc705
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Initialisation des tableaux
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si une classe a un constructeur, les tableaux de cette classe sont initialisés par un constructeur. S'il y a moins d'éléments dans la liste d'initialiseurs que les éléments du tableau, le constructeur par défaut est utilisé pour les éléments restants. Si aucun constructeur par défaut n'est défini pour la classe, la liste d'initialiseurs doit être complète (autrement dit, il doit y avoir un initialiseur pour chaque élément du tableau.)  
  
 Prenons la classe `Point` qui définit deux constructeurs :  
  
```  
// initializing_arrays1.cpp  
class Point  
{  
public:  
   Point()   // Default constructor.  
   {  
   }  
   Point( int, int )   // Construct from two ints  
   {  
   }  
};  
  
// An array of Point objects can be declared as follows:  
Point aPoint[3] = {  
   Point( 3, 3 )     // Use int, int constructor.  
};  
  
int main()  
{  
}  
```  
  
 Le premier élément de `aPoint` est construit en utilisant le constructeur `Point( int, int )`. Les deux éléments restants sont construits à l'aide du constructeur par défaut.  
  
 Tableaux membres statiques (si **const** ou non) peuvent être initialisés dans leurs définitions (en dehors de la déclaration de classe). Exemple :  
  
```  
// initializing_arrays2.cpp  
class WindowColors  
{  
public:  
    static const char *rgszWindowPartList[7];  
};  
  
const char *WindowColors::rgszWindowPartList[7] = {  
    "Active Title Bar", "Inactive Title Bar", "Title Bar Text",  
    "Menu Bar", "Menu Bar Text", "Window Background", "Frame"   };  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [(NOTINBUILD) Fonctions membres spéciales](http://msdn.microsoft.com/fr-fr/82223d73-64cb-4923-b678-78f9568ff3ca)