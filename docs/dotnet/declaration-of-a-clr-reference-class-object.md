---
title: "D&#233;claration d&#39;un objet de classe de r&#233;f&#233;rence du CLR | Microsoft Docs"
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
helpviewer_keywords: 
  - "types référence, CLR"
  - "types (C++), types référence"
ms.assetid: 6d64f746-3715-4948-ada3-88859f4150e4
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;claration d&#39;un objet de classe de r&#233;f&#233;rence du CLR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La syntaxe servant à déclarer et à instancier un objet d'un type de classe de référence a été modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 Dans Extensions managées, un objet de type de classe de référence se déclare à l'aide de la syntaxe de pointeur d'ISO\-C\+\+, avec la possibilité d'utiliser en option le mot clé `__gc` à gauche de l'étoile \(`*`.  Voici, par exemple, plusieurs déclarations d'objets de type de classe de référence sous la syntaxe d'Extensions managées :  
  
```  
public __gc class Form1 : public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container __gc *components;  
   Button __gc *button1;  
   DataGrid __gc *myDataGrid;     
   DataSet __gc *myDataSet;  
  
   void PrintValues( Array* myArr ) {  
      System::Collections::IEnumerator* myEnumerator =   
         myArr->GetEnumerator();  
  
      Array *localArray;  
      myArr->Copy(myArr, localArray, myArr->Length);  
   }  
};  
```  
  
 Avec la nouvelle syntaxe, un objet de type de classe de référence se déclare à l'aide d'un nouveau jeton déclaratif \(`^`\) appelé officiellement *handle de suivi* et plus couramment *chapeau*. \(L'adjectif « suivi » souligne l'idée qu'un type référence se trouve dans le tas du CLR et peut par conséquent changer d'emplacement de façon transparente pendant le compactage du tas du garbage collection.  Les handles de suivi sont mis à jour de façon transparente au cours de l'exécution.  Deux concepts analogues sont le *suivi des références* \(`%`\), et le *pointeur intérieur* \(`interior_ptr<>`\), traités dans [Sémantique de type valeur](../dotnet/value-type-semantics.md).  
  
 Il existe deux raisons essentielles d'éloigner la syntaxe déclarative d'une réutilisation de la syntaxe de pointeur ISO\-C\+\+ :  
  
-   L'utilisation de la syntaxe de pointeur ne permettait pas que les opérateurs surchargés soient directement appliqués à un objet de référence.  Il fallait, à la place, appeler l'opérateur en utilisant son nom interne, tel que `rV1->op_Addition(rV2)` au lieu du nom `rV1+rV2` plus intuitif.  
  
-   Plusieurs opérations de pointeur, telles que les casts et les opérations arithmétiques sur les pointeurs, n'autorisaient pas les objets stockés sur un tas récupéré par le garbage collector.  La notion de handle de suivi exprimait mieux la nature d'un type référence du CLR.  
  
 Le modificateur `__gc` sur un handle de suivi est inutile et n'est pas pris en charge.  L'utilisation de l'objet lui\-même n'est pas modifiée ; celui\-ci accède encore aux membres via l'opérateur de sélection de membre pointeur \(`->`\).  Par exemple, voici l'exemple de code Extensions managées précédent traduit dans la nouvelle syntaxe :  
  
```  
public ref class Form1: public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container^ components;  
   Button^ button1;  
   DataGrid^ myDataGrid;  
   DataSet^ myDataSet;  
  
   void PrintValues( Array^ myArr ) {  
      System::Collections::IEnumerator^ myEnumerator =  
         myArr->GetEnumerator();  
  
      Array ^localArray;  
      myArr->Copy(myArr, localArray, myArr->Length);   }  
};  
```  
  
## Allocation dynamique d'un objet sur le tas du CLR  
 Dans Extensions managées, l'existence de deux expressions `new` à allouer entre le tas natif et le tas managé était en grande partie transparente.  Dans presque toutes instances, le compilateur est capable d'utiliser le contexte pour déterminer s'il faut allouer la mémoire à partir du tas natif ou du tas managé.  Par exemple :  
  
```  
Button *button1 = new Button; // OK: managed heap  
int *pi1 = new int;           // OK: native heap  
Int32 *pi2 = new Int32;       // OK: managed heap  
```  
  
 Lorsque vous ne souhaitez pas l'allocation de tas contextuelle, vous pouvez diriger le compilateur avec le mot clé `__gc` ou `__nogc`.  Dans la nouvelle syntaxe, la nature distincte des deux nouvelles expressions est rendue explicite par l'introduction du mot clé `gcnew`.  Par exemple, les trois déclarations ci\-dessus prennent dans la nouvelle syntaxe l'aspect suivant :  
  
```  
Button^ button1 = gcnew Button;        // OK: managed heap  
int * pi1 = new int;                   // OK: native heap  
Int32^ pi2 = gcnew Int32; // OK: managed heap  
```  
  
 Voici l'initialisation en Extensions managées des membres `Form1` déclarés dans la section précédente :  
  
```  
void InitializeComponent() {  
   components = new System::ComponentModel::Container();  
   button1 = new System::Windows::Forms::Button();  
   myDataGrid = new DataGrid();  
  
   button1->Click +=   
      new System::EventHandler(this, &Form1::button1_Click);  
}  
```  
  
 Voici la même initialisation remodelée par la nouvelle syntaxe.  Notez que le chapeau n'est pas requis pour le type référence lorsque celui\-ci est la cible d'une expression `gcnew`.  
  
```  
void InitializeComponent() {  
   components = gcnew System::ComponentModel::Container;  
   button1 = gcnew System::Windows::Forms::Button;  
   myDataGrid = gcnew DataGrid;  
  
   button1->Click +=   
      gcnew System::EventHandler( this, &Form1::button1_Click );  
}  
```  
  
## Une référence de suivi à aucun objet  
 Dans la nouvelle syntaxe, `0` ne représente plus une adresse ayant la valeur null, mais est traité comme un entier, de même que `1`, `10`, ou `100`.  Un nouveau jeton spécial représente une valeur null pour une référence de suivi.  Par exemple, en Extensions managées, on initialise un type référence pour n'adresser aucun objet, comme ceci :  
  
```  
// OK: we set obj to refer to no object  
Object * obj = 0;  
  
// Error: no implicit boxing  
Object * obj2 = 1;  
```  
  
 Dans la nouvelle syntaxe, toute initialisation ou assignation d'un type valeur à un `Object` entraîne la conversion boxing implicite de ce type valeur.  Dans la nouvelle syntaxe, `obj` et `obj2` sont initialisés en objets Int32 boxed adressés qui prennent respectivement les valeurs 0 et 1.  Par exemple :  
  
```  
// causes the implicit boxing of both 0 and 1  
Object ^ obj = 0;  
Object ^ obj2 = 1;  
```  
  
 Pour autoriser l'initialisation, l'assignation et la comparaison explicites d'un handle de suivi vers une valeur nulle, utilisez un nouveau mot clé, `nullptr`.  La révision correcte de l'exemple d'origine devient ainsi la suivante :  
  
```  
// OK: we set obj to refer to no object  
Object ^ obj = nullptr;  
  
// OK: we initialize obj2 to a Int32^  
Object ^ obj2 = 1;  
```  
  
 Cela complique quelque peu le portage du code existant vers la nouvelle syntaxe.  Par exemple, considérons la déclaration de classe value suivante :  
  
```  
__value struct Holder {  
   Holder( Continuation* c, Sexpr* v ) {  
      cont = c;  
      value = v;  
      args = 0;  
      env = 0;  
   }  
  
private:  
   Continuation* cont;  
   Sexpr * value;  
   Environment* env;  
   Sexpr * args __gc [];  
};  
```  
  
 Dans ce cas, `args` et `env` sont des types référence du CLR.  L'initialisation de ces deux membres à `0` dans le constructeur ne peut pas rester inchangée dans la transition vers la nouvelle syntaxe.  Elle doit plutôt devenir `nullptr`:  
  
```  
value struct Holder {  
   Holder( Continuation^ c, Sexpr^ v )  
   {  
      cont = c;  
      value = v;  
      args = nullptr;  
      env = nullptr;  
   }  
  
private:  
   Continuation^ cont;  
   Sexpr^ value;  
   Environment^ env;  
   array<Sexpr^>^ args;  
};  
```  
  
 De même, les tests consistant à comparer ces membres à `0` doivent également être modifiés pour qu'ils soient désormais comparés à `nullptr`.  Voici la syntaxe en Extensions managées :  
  
```  
Sexpr * Loop (Sexpr* input) {  
   value = 0;  
   Holder holder = Interpret(this, input, env);  
  
   while (holder.cont != 0) {  
      if (holder.env != 0) {  
         holder=Interpret(holder.cont,holder.value,holder.env);  
      }  
      else if (holder.args != 0) {  
         holder =   
         holder.value->closure()->  
         apply(holder.cont,holder.args);  
      }  
   }  
  
   return value;  
}  
```  
  
 Voici la révision qui transforme chaque instance de `0` en un `nullptr`.  \(Les outils de traduction aident à effectuer cette transformation en automatisant un grand nombre d'occurrences \(pas toutes\), notamment à l'aide de la macro `NULL`.\)  
  
```  
Sexpr ^ Loop (Sexpr^ input) {  
   value = nullptr;  
   Holder holder = Interpret(this, input, env);  
  
   while ( holder.cont != nullptr ) {  
      if ( holder.env != nullptr ) {  
         holder=Interpret(holder.cont,holder.value,holder.env);  
      }  
      else if (holder.args != nullptr ) {  
         holder =   
         holder.value->closure()->  
         apply(holder.cont,holder.args);  
      }  
   }  
  
   return value;  
}  
```  
  
 Le `nullptr` est converti en un pointeur ou un type de handle de suivi, mais ne devient pas un type intégral.  Par exemple, dans le jeu suivant d'initialisations, le `nullptr` n'est valide en tant que valeur initiale que pour les deux premiers jeux.  
  
```  
// OK: we set obj and pstr to refer to no object  
Object^ obj = nullptr;  
char*   pstr = nullptr; // 0 would also work here  
  
// Error: no conversion of nullptr to 0 …  
int ival = nullptr;  
```  
  
 De même, étant donné un jeu surchargé de méthodes tel que ceci :  
  
```  
void f( Object^ ); // (1)  
void f( char* );   // (2)  
void f( int );     // (3)  
```  
  
 Un appel avec un littéral `nullptr`, tel que :  
  
```  
// Error: ambiguous: matches (1) and (2)  
f(  nullptr );  
```  
  
 est ambigu parce que le `nullptr` correspond à la fois à un handle de suivi et un pointeur et qu'aucune préférence n'est donnée à un type par rapport à l'autre. \(Il faut recourir à un cast explicite pour lever l'ambiguïté\).  
  
 Un appel avec `0` correspond exactement à l'instance \(3\) :  
  
```  
// OK: matches (3)  
f( 0 );  
```  
  
 parce qu'un `0` est de type entier.  Si `f(int)` n'était pas présent, l'appel correspondrait clairement à `f(char*)` via une conversion standard.  Les règles correspondantes donnent la priorité à une correspondance exacte par rapport à une conversion standard.  En l'absence de correspondance exacte, une conversion standard reçoit priorité sur une conversion boxing implicite d'un type valeur.  C'est pourquoi il n'y a aucune ambiguïté.  
  
## Voir aussi  
 [Types managés \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Handle sur l'opérateur Object \(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)