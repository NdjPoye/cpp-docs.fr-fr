---
title: "delete, op&#233;rateur (C++) | Microsoft Docs"
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
  - "delete_cpp"
  - "delete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "delete (mot clé) (C++)"
  - "delete (mot clé) (C++), libérer des objets"
  - "delete (mot clé) (C++), syntaxe"
ms.assetid: de39c900-3f57-489c-9598-dcb73c4b3930
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# delete, op&#233;rateur (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Libère un bloc de mémoire.  
  
## Syntaxe  
  
```  
[::] delete cast-expression  
[::] delete [ ] cast-expression  
```  
  
## Notes  
 L'argument *cast\-expression* doit être un pointeur vers un bloc de mémoire précédemment alloué pour un objet créé avec l'[opérateur new](../cpp/new-operator-cpp.md).  L'opérateur **delete** a un résultat de type `void` et ne retourne par conséquent pas de valeur.  Exemple :  
  
```  
CDialog* MyDialog = new CDialog;  
// use MyDialog  
delete MyDialog;  
```  
  
 L'utilisation de **delete** sur un pointeur vers un objet non alloué avec **new** donne des résultats imprévisibles.  Toutefois, vous pouvez utiliser **delete** sur un pointeur avec la valeur 0.  Cette configuration signifie que, quand **new** retourne 0 en cas d'échec, la suppression du résultat d'une opération **new** ayant échoué ne présente aucun danger.  Pour plus d'informations, consultez [Opérateurs new et delete](../cpp/new-and-delete-operators.md).  
  
 Les opérateurs **new** et **delete** peuvent également être utilisés pour les types intégrés, y compris les tableaux.  Si `pointer` fait référence à un tableau, placez des crochets vides avant `pointer` :  
  
```  
int* set = new int[100];  
//use set[]  
delete [] set;  
```  
  
 L'utilisation de l'opérateur **delete** sur un objet libère sa mémoire.  Un programme qui déréférence un pointeur après la suppression de l'objet peut avoir des résultats imprévisibles ou se bloquer.  
  
 Quand **delete** est utilisé pour libérer la mémoire pour un objet de classe C\+\+, le destructeur de l'objet est appelé avant la libération de la mémoire de l'objet \(si l'objet a un destructeur\).  
  
 Si l'opérande de l'opérateur **delete** est une l\-value modifiable, sa valeur n'est pas définie une fois que l'objet est supprimé.  
  
## Utilisation de delete  
 Il existe deux variantes syntaxiques pour l'[opérateur delete](../cpp/delete-operator-cpp.md) : une pour les objets uniques, l'autre pour les tableaux d'objets.  Le fragment de code suivant illustre les différences entre ces variantes :  
  
```  
// expre_Using_delete.cpp  
struct UDType   
{  
};  
  
int main()  
{  
   // Allocate a user-defined object, UDObject, and an object  
   //  of type double on the free store using the  
   //  new operator.  
   UDType *UDObject = new UDType;  
   double *dObject = new double;  
   // Delete the two objects.  
   delete UDObject;  
   delete dObject;   
   // Allocate an array of user-defined objects on the  
   // free store using the new operator.  
   UDType (*UDArr)[7] = new UDType[5][7];  
   // Use the array syntax to delete the array of objects.  
   delete [] UDArr;  
}  
```  
  
 Les deux cas suivants génèrent des résultats indéfinis : en utilisant la forme de tableau delete \(delete \[ \]\) sur un objet et en utilisant la forme nonarray de delete sur un tableau.  
  
## Exemple  
 Pour obtenir des exemples d'utilisation de **delete**, consultez [new, opérateur](../cpp/new-operator-cpp.md).  
  
## Fonctionnement de delete  
 L'[opérateur delete](../cpp/delete-operator-cpp.md) appelle la fonction [operator delete](../misc/operator-delete-function.md).  
  
 Pour les objets qui ne sont pas de type classe \([classe](../cpp/class-cpp.md), [struct](../cpp/struct-cpp.md) ou [union](../cpp/unions.md)\), l'opérateur delete global est appelé.  Pour les objets de type classe, le nom de la fonction de désallocation est résolu dans la portée globale si l'expression de suppression commence par l'opérateur de résolution de portée unaire \(::\).  Sinon, l'opérateur delete appelle le destructeur pour un objet avant de désallouer la mémoire \(si le pointeur n'est pas null\).  L'opérateur delete peut être défini pour chaque classe ; si cette définition n'existe pas pour une classe donnée, l'opérateur de suppression global est appelé.  Si l'expression de suppression est utilisée pour désallouer un objet de classe dont le type statique a un destructeur virtuel, la fonction de désallocation est résolue par l'intermédiaire du destructeur virtuel du type dynamique de l'objet.  
  
## Voir aussi  
 [Expressions avec opérateurs unaires](../cpp/expressions-with-unary-operators.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Opérateurs new et delete](../cpp/new-and-delete-operators.md)   
 [Fonction de l'opérateur delete](../misc/operator-delete-function.md)