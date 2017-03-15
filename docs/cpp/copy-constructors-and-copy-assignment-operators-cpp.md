---
title: "Constructeurs de copie et op&#233;rateurs d&#39;assignation de copie (C++) | Microsoft Docs"
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
  - "= (opérateur), copier des objets"
  - "assigner des valeurs à des objets copiés"
  - "opérateurs d'assignation, pour copier des objets"
  - "instructions d'assignation, copier des objets"
  - "copier des objets"
  - "initialiser des objets, par des objets copiés"
  - "objets (C++), copier"
ms.assetid: a94fe1f9-0289-4fb9-8633-77c654002c0d
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Constructeurs de copie et op&#233;rateurs d&#39;assignation de copie (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  À partir de C\+\+11, deux types d'assignations sont pris en charge dans le langage : *assignation de copie* et *assignation de déplacement*.  Dans cet article « assignation » signifie assignation de copie, sauf spécification contraire.  Pour plus d'informations sur l'assignation de déplacement, consultez [Constructeurs de déplacement et opérateurs d'assignation de déplacement \(C\+\+\)](http://msdn.microsoft.com/fr-fr/1442de5f-37a5-42a1-83a6-ec9cfe0414db).  
>   
>  Les opérations d'assignation et d'initialisation génèrent une copie des objets.  
  
-   **Assignation** : Lorsque la valeur d'un objet est assignée à un autre objet, le premier objet est copié dans le second.  Par conséquent,  
  
    ```cpp  
    Point a, b;  
    ...  
    a = b;  
    ```  
  
     entraîne la copie de la valeur de `b` dans `a`.  
  
-   **Initialisation** : L'initialisation se produit lorsqu'un nouvel objet est déclaré, lorsque des arguments sont transmis à des fonctions par valeur, ou lorsque des valeurs sont retournées par les fonctions par valeur.  
  
 Vous pouvez définir la sémantique de « copie » pour les objets de type classe.  Par exemple, prenons le code suivant :  
  
```cpp  
TextFile a, b;  
a.Open( "FILE1.DAT" );  
b.Open( "FILE2.DAT" );  
b = a;  
```  
  
 Ce code pourrait signifier « copier le contenu de FILE1.DAT vers FILE2.DAT » ou « ignorer FILE2.DAT et faire de `b` un deuxième handle vers FILE1.DAT ». Vous devez lier à chaque classe la sémantique de copie appropriée, comme suit.  
  
-   En utilisant l'opérateur d'assignation `operator=` avec une référence au type de classe comme type de retour et au paramètre transmis par la référence `const` ; par exemple, `ClassName& operator=(const ClassName& x);`.  
  
-   En utilisant le constructeur de copie.  Pour plus d'informations sur le constructeur de copie, consultez [Règles de déclaration des constructeurs](../misc/rules-for-declaring-constructors.md).  
  
 Si vous ne déclarez pas de constructeur de copie, le compilateur génère un constructeur de copie de membre à membre à votre place.  Si vous ne déclarez pas d'opérateur d'assignation de copie, le compilateur génère un opérateur d'assignation de copie de membre à membre à votre place. La déclaration d'un constructeur de copie n'entraîne pas la suppression de l'opérateur d'assignation de copie généré par le compilateur, et vice versa.  Si vous implémentez l'un des deux, nous vous recommandons d'implémenter également l'autre afin que la signification du code soit claire.  
  
 L'assignation de membre à membre est décrite plus en détail dans [\(NOTINBUILD\) Memberwise Assignment and Initialization](http://msdn.microsoft.com/fr-fr/94048213-8b49-4416-8069-b1b7a6f271f9).  
  
 Le constructeur de copie utilise un argument de type *class\-name***&**, où *class\-name* est le nom de la classe pour laquelle le constructeur est défini.  Exemple :  
  
```cpp  
// spec1_copying_class_objects.cpp  
class Window  
{  
public:  
    Window( const Window& ); // Declare copy constructor.  
    // ...  
};  
  
int main()  
{  
}  
```  
  
> [!NOTE]
>  Utilisez le type d'argument *const class\-name***&** pour le constructeur de copie chaque fois que possible.  Cela empêche le constructeur de copie de modifier accidentellement l'objet à partir duquel il effectue la copie.  Cela permet également d'effectuer une copie à partir des objets **const**.  
  
## Constructeurs de copie générés par le compilateur  
 Les constructeurs de copie générés par le compilateur, comme les constructeurs de copie définis par l'utilisateur, ont un seul argument de type « référence à *class\-name* ». Toutefois, cette règle ne se vérifie pas lorsque toutes les classes de base et les classes de membre possèdent des constructeurs de copie déclarés comme prenant un argument unique de type **const** *class\-name***&**.  Dans ce cas, l'argument du constructeur de copie généré par le compilateur est également **const**.  
  
 Lorsque le type d'argument du constructeur de copie n'est pas **const**, l'initialisation via la copie d'un objet **const** génère une erreur.  L'inverse est impossible : si l'argument est **const**, vous pouvez initialiser en copiant un objet qui n'est pas **const**.  
  
 Les opérateurs d'assignation générés par le compilateur suivent le même modèle en ce qui concerne **const** Ils acceptent un argument unique de type *class\-name***&** à moins que les opérateurs d'assignation dans toutes les classes de base et les classes de membre n'acceptent des arguments du type **const** *class\-name&.* Dans ce cas, l'opérateur d'assignation généré de la classe prend un argument **const**.  
  
> [!NOTE]
>  Lorsque des classes de base virtuelles sont initialisées par des constructeurs de copie, générés par le compilateur ou définis par l'utilisateur, elles ne sont initialisées qu'une seule fois : au moment où elles sont construites.  
  
 Les conséquences sont semblables à celles du constructeur de copie.  Lorsque le type d'argument n'est pas **const**, l'assignation d'un objet **const** génère une erreur.  L'inverse est impossible : si une valeur **const** est assignée à une valeur qui n'est pas **const**, l'assignation réussit.  
  
 Pour plus d'informations sur les opérateurs d'assignation surchargés, consultez [Assignation](../cpp/assignment.md).  
  
## Voir aussi  
 [Fonctions membres spéciales](../misc/special-member-functions-cpp.md)