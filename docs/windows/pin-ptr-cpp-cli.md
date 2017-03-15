---
title: "pin_ptr (C++/CLI) | Microsoft Docs"
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
  - "pin_ptr_cpp"
  - "stdcli::language::pin_ptr"
  - "pin_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pinning pointers"
  - "pin_ptr keyword [C++]"
ms.assetid: 6c2e6c73-4ec2-4dce-8e1f-ccf3a9f9d0aa
caps.latest.revision: 28
caps.handback.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# pin_ptr (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Déclare un *pointeur épingle*, qui est utilisé uniquement avec le CLR.  
  
## Tous les runtimes  
 \(Aucune note de cette fonctionnalité de langage ne s'applique à tous les runtimes.\)  
  
## Windows Runtime  
 \(Cette fonctionnalité des langages n'est pas prise en charge dans les fenêtres d'exécution.\)  
  
## Common Language Runtime  
 Un *pointeur épingle* est un pointeur interieur qui empêche l'objet désigné de bouger sur le segment récupéré par le garbage collector.  Autrement dit, la valeur d'un pointeur épingle n'est pas modifiée par le CLR.  Cela est necessaire lors de la transmission de l'adresse d'une classe managée à une fonction non managée pour que l'adresse ne change pas de manière inattendue pendant la résolution de l'appel de fonction non managé.  
  
### Syntaxe  
  
```cpp  
[cli::]pin_ptr<cv_qualifier type> var = &initializer;  
```  
  
### Paramètres  
 *cv\_qualifier*  
 `const` ou identificateurs `volatile`.  Par défaut, un pointeur épingle est `volatile`.  C'est redondant mais pas une erreur pour déclarer un pointeur épingle `volatile`.  
  
 *type*  
 Type de `initializer`.  
  
 *var*  
 Nom de la variable `pin_ptr`.  
  
 *initializer*  
 Un membre d'un type de référence, un élément d'un tableau managé, ou tout autre objet que vous pouvez attribuer à un pointeur natif.  
  
### Remarques  
 Un `pin_ptr` représente un surensemble des fonctionnalités d'un pointeur natif.  Par conséquent, un problème susceptible d'être affecté à un pointeur natif peut également être affecté à un `pin_ptr`.  Un pointeur intérieur est autorisé à exécuter le même ensemble d'opérations que les pointeurs natifs, notamment la comparaison et retourner les opérations arithmétiques sur les pointeurs.  
  
 Objet ou sous\-objet d'une classe managée peut être masquée lorsqu'elle, auquel cas le common langage runtime la ne descendra pas pendant le garbage collection.  L'utilisation principale de cela est de transmettre un pointeur vers les données gérées comme paramètre effectif d'un appel de fonction managé.  Lors d'un cycle de collection, l'exécution inspectera les métadonnées créées pour le pointeur épingle et ne descendra pas l'élément qu'il pointe.  
  
 Épinglant objet épingle également les champs de valeurs ; autrement dit, champs de primitive ou du type de valeur.  Toutefois, les champs déclarés par le handle de suivi \(`%`\) ne sont pas épinglés.  
  
 Épingler un sous\-objet défini dans un objet managé a pour effet d'épingler l'objet entier.  
  
 Si le pointeur épingle est réaffecté pour indiquer une nouvelle valeur, l'instance précédente désignée n'est plus vu comme épinglée.  
  
 Objet est épinglé uniquement lorsque des points `pin_ptr` lui.  L'objet n'est plus épinglé lorsque son pointeur épingle sort de l'étendue, ou a la valeur [nullptr](../windows/nullptr-cpp-component-extensions.md).  Après que `pin_ptr` sorte hors de portée, l'objet qui a été épinglé peut être déplacé dans le segment par le garbage collector.  Aucun pointeur natif qui affiche toujours l'objet ne sera mis à jour, et déréférençant l'un d'eux peut lever une exception irrécupérable.  
  
 Si aucun pointeurs épingle ne pointe sur l'objet \(tous les pointeurs épingle sont générés de l'étendue, ont été attribués à nouveau pour afficher d'autres objets, ou on ont été affectés [nullptr](../windows/nullptr-cpp-component-extensions.md)\), l'objet n'est garanti ne pas être épinglé.  
  
 Un pointeur épingler peut pointer vers un handle de référence, un type de valeur, ou un handle enfermé dans une boîte de type, un membre d'un type managé, ou un élément d'un tableau managé.  Il ne peut pas pointer vers un type de référence.  
  
 Accepter l'adresse `pin_ptr` qui indique un objet natif d'origine du comportement n'est pas définie.  
  
 Les pointeurs épingle peuvent être déclarés en tant que variables locales statiques dans la pile.  
  
 Les pointeurs épingle ne peuvent pas être utilisés comme suit :  
  
-   paramètres de fonction  
  
-   le type de retour d'une fonction  
  
-   le membre d'une classe  
  
-   le type de la cible d'une empreinte  
  
 `pin_ptr` est dans l'espace de noms `cli`.  Pour plus d'informations, consultez [Platform, default, and cli Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
 Pour plus d'informations sur les pointeurs intérieurs, consultez [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md).  
  
 Pour plus d'informations sur les pointeurs épingles, consultez [How to: Pin Pointers and Arrays](../windows/how-to-pin-pointers-and-arrays.md) et [How to: Declare Pinning Pointers and Value Types](../windows/how-to-declare-pinning-pointers-and-value-types.md).  
  
### Conditions requises  
 Option du compilateur : **\/clr**  
  
### Exemples  
 **Exemple**  
  
 L'exemple suivant utilise `pin_ptr` pour limiter la position du premier élément d'un tableau.  
  
```  
// pin_ptr_1.cpp  
// compile with: /clr   
using namespace System;  
#define SIZE 10  
  
#pragma unmanaged  
// native function that initializes an array  
void native_function(int* p) {  
   for(int i = 0 ; i < 10 ; i++)  
    p[i] = i;  
}  
#pragma managed  
  
public ref class A {  
private:  
   array<int>^ arr;   // CLR integer array  
  
public:  
   A() {  
      arr = gcnew array<int>(SIZE);  
   }  
  
   void load() {  
   pin_ptr<int> p = &arr[0];   // pin pointer to first element in arr  
   int* np = p;   // pointer to the first element in arr  
   native_function(np);   // pass pointer to native function  
   }  
  
   int sum() {  
      int total = 0;  
      for (int i = 0 ; i < SIZE ; i++)  
         total += arr[i];  
      return total;  
   }  
};  
  
int main() {  
   A^ a = gcnew A;  
   a->load();   // initialize managed array using the native function  
   Console::WriteLine(a->sum());  
}  
```  
  
 **Sortie**  
  
  **45** **Exemple**  
  
 L'exemple suivant montre un pointeur intérieur qui peut être converti en un pointeur épingle, ainsi que le type de retour de l'opérateur d'adresse \(`&`\) pointeur intérieur si l'opérande est sur le segment managé.  
  
```  
// pin_ptr_2.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct G {  
   G() : i(1) {}  
   int i;  
};  
  
ref struct H {  
   H() : j(2) {}  
   int j;  
};  
  
int main() {  
   G ^ g = gcnew G;   // g is a whole reference object pointer  
   H ^ h = gcnew H;  
  
   interior_ptr<int> l = &(g->i);   // l is interior pointer  
  
   pin_ptr<int> k = &(h->j);   // k is a pinning interior pointer  
  
   k = l;   // ok  
   Console::WriteLine(*k);  
};  
```  
  
 **Sortie**  
  
 **1** **Exemple**  
  
 L'exemple suivant montre un pointeur épingle peut être converti en un autre type.  
  
```  
// pin_ptr_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class ManagedType {  
public:  
   int i;  
};  
  
int main() {  
   ManagedType ^mt = gcnew ManagedType;  
   pin_ptr< int > pt = &mt->i;  
   *pt = 8;  
   Console::WriteLine(mt->i);  
  
   char *pc = ( char* ) pt;  
   *pc = 255;  
   Console::WriteLine(mt->i);  
}  
```  
  
 **Sortie**  
  
 **8**   
**255**