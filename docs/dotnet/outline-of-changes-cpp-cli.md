---
title: "Plan des modifications (C++/CLI) | Microsoft Docs"
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
ms.assetid: c0bbbd6b-c5c4-44cf-a6ca-c1010c377e9d
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Plan des modifications (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ce plan propose des exemples de quelques\-unes des modifications du langage entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  Suivez le lien qui accompagne chaque élément pour obtenir plus d'informations.  
  
## Aucun mot clé à trait de soulignement double  
 Le trait de soulignement double qui précède tous les mots clés a été supprimé, à une exception près.  Donc, `__value` devient `value` et `__interface` devient `interface`, etc.  Pour empêcher des conflits de nom entre des mots clés et des identificateurs dans le code utilisateur, les mots clés sont essentiellement traités comme contextuels.  
  
 Pour plus d'informations, consultez [Mots clés de langage \(C\+\+\/CLI\)](../dotnet/language-keywords-cpp-cli.md).  
  
## Déclarations de classe  
 Syntaxe des Extensions managées :  
  
```  
__gc class Block {};                           // reference class  
__value class Vector {};                       // value class  
__interface I {};                        // interface class  
__gc __abstract class Shape {};                // abstract class  
__gc __sealed class Shape2D : public Shape {}; // derived class  
```  
  
 Nouvelle syntaxe :  
  
```  
ref class Block {};                // reference class  
value class Vector {};             // value class  
interface class I {};        // interface class  
ref class Shape abstract {};       // abstract class  
ref class Shape2D sealed: Shape{}; // derived class  
```  
  
 Pour plus d'informations, consultez [Types managés \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md).  
  
## Déclaration d'objet  
 Syntaxe des Extensions managées :  
  
```  
public __gc class Form1 : public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container __gc *components;  
   System::Windows::Forms::Button   __gc *button1;  
   System::Windows::Forms::DataGrid __gc *myDataGrid;     
   System::Data::DataSet  __gc *myDataSet;  
};  
```  
  
 Nouvelle syntaxe :  
  
```  
public ref class Form1 : System::Windows::Forms::Form {  
   System::ComponentModel::Container^ components;  
   System::Windows::Forms::Button^ button1;  
   System::Windows::Forms::DataGrid^ myDataGrid;  
   System::Data::DataSet^ myDataSet;  
};  
```  
  
 Pour plus d'informations, consultez [Déclaration d'un objet de classe de référence du CLR](../dotnet/declaration-of-a-clr-reference-class-object.md).  
  
### Allocation de tas géré  
 Syntaxe des Extensions managées :  
  
```  
Button* button1 = new Button; // managed heap  
int *pi1 = new int;           // native heap  
Int32 *pi2 = new Int32;       // managed heap  
```  
  
 Nouvelle syntaxe :  
  
```  
Button^ button1 = gcnew Button;        // managed heap  
int * pi1 = new int;                   // native heap  
Int32^ pi2 = gcnew Int32;              // managed heap  
```  
  
 Pour plus d'informations, consultez [Déclaration d'un objet de classe de référence du CLR](../dotnet/declaration-of-a-clr-reference-class-object.md).  
  
### Une référence de suivi à aucun objet  
 Syntaxe des Extensions managées :  
  
```  
// OK: we set obj to refer to no object  
Object * obj = 0;  
  
// Error: no implicit boxing  
Object * obj2 = 1;  
```  
  
 Nouvelle syntaxe :  
  
```  
// Incorrect Translation  
// causes the implicit boxing of both 0 and 1  
Object ^ obj = 0;  
Object ^ obj2 = 1;  
  
// Correct Translation  
// OK: we set obj to refer to no object  
Object ^ obj = nullptr;  
  
// OK: we initialize obj2 to an Int32^  
Object ^ obj2 = 1;  
```  
  
 Pour plus d'informations, consultez [Déclaration d'un objet de classe de référence du CLR](../dotnet/declaration-of-a-clr-reference-class-object.md).  
  
## Déclaration de tableau  
 Le tableau CLR a été refondu.  Il est similaire à la collection de modèles `vector` stl, mais correspond à la classe `System::Array` sous\-jacente – autrement dit, il ne s'agit pas d'une implémentation de modèle.  
  
 Pour plus d'informations, consultez [Déclaration d'un tableau CLR](../dotnet/declaration-of-a-clr-array.md).  
  
### Tableau comme paramètre  
 Syntaxe de tableau des extensions managées :  
  
```  
void PrintValues( Object* myArr __gc[]);   
void PrintValues( int myArr __gc[,,]);   
```  
  
 Nouvelle syntaxe de tableau :  
  
```  
void PrintValues( array<Object^>^ myArr );  
void PrintValues( array<int,3>^ myArr );  
```  
  
### Tableau comme type de retour  
 Syntaxe de tableau des extensions managées :  
  
```  
Int32 f() [];   
int GetArray() __gc[];  
```  
  
 Nouvelle syntaxe de tableau :  
  
```  
array<Int32>^ f();  
array<int>^ GetArray();  
```  
  
### Initialisation abrégée de tableau CLR local  
 Syntaxe de tableau des extensions managées :  
  
```  
int GetArray() __gc[] {  
   int a1 __gc[] = { 1, 2, 3, 4, 5 };  
   Object* myObjArray __gc[] = { __box(26), __box(27), __box(28),  
                                 __box(29), __box(30) };  
  
   return a1;  
}  
```  
  
 Nouvelle syntaxe de tableau :  
  
```  
array<int>^ GetArray() {  
   array<int>^ a1 = {1,2,3,4,5};  
   array<Object^>^ myObjArray = {26,27,28,29,30};  
  
   return a1;  
}  
```  
  
### Déclaration de tableau CLR explicite  
 Syntaxe de tableau des extensions managées :  
  
```  
Object* myArray[] = new Object*[2];  
String* myMat[,] = new String*[4,4];  
```  
  
 Nouvelle syntaxe de tableau :  
  
```  
array<Object^>^ myArray = gcnew array<Object^>(2);  
array<String^,2>^ myMat = gcnew array<String^,2>(4,4);  
```  
  
 Nouveauté du langage : initialisation de tableau explicite à la suite de gcnew  
  
```  
// explicit initialization list follow gcnew   
// is not supported in Managed Extensions  
array<Object^>^ myArray =   
   gcnew array<Object^>(4){ 1, 1, 2, 3 };  
```  
  
## Propriétés scalaires  
 Syntaxe des propriétés en Extensions managées :  
  
```  
public __gc __sealed class Vector {  
   double _x;  
  
public:  
   __property double get_x(){ return _x; }  
   __property void set_x( double newx ){ _x = newx; }  
};  
```  
  
 Nouvelle syntaxe des propriétés :  
  
```  
public ref class Vector sealed {   
   double _x;  
  
public:  
   property double x   
   {  
      double get()             { return _x; }  
      void   set( double newx ){ _x = newx; }  
   } // Note: no semi-colon …  
};  
```  
  
 Nouveauté du langage : propriétés triviales  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   // backing store is not accessible  
   property double x;   
};  
```  
  
 Pour plus d'informations, consultez [Déclaration de propriété](../dotnet/property-declaration.md).  
  
## Propriétés indexées  
 Syntaxe des propriétés indexées en Extensions managées :  
  
```  
public __gc class Matrix {  
   float mat[,];  
  
public:   
   __property void set_Item( int r, int c, float value) { mat[r,c] = value; }  
   __property int get_Item( int r, int c ) { return mat[r,c]; }  
};  
```  
  
 Nouvelle syntaxe des propriétés indexées :  
  
```  
public ref class Matrix {  
   array<float, 2>^ mat;  
  
public:  
   property float Item [int,int] {  
      float get( int r, int c ) { return mat[r,c]; }  
      void set( int r, int c, float value ) { mat[r,c] = value; }  
   }  
};  
```  
  
 Nouveauté du langage : propriété indexée de niveau de classe  
  
```  
public ref class Matrix {  
   array<float, 2>^ mat;  
  
public:  
   // ok: class level indexer now  
   //     Matrix mat;  
   //     mat[ 0, 0 ] = 1;   
   //  
   // invokes the set accessor of the default indexer  
  
   property float default [int,int] {  
      float get( int r, int c ) { return mat[r,c]; }  
      void set( int r, int c, float value ) { mat[r,c] = value; }  
   }  
};  
```  
  
 Pour plus d'informations, consultez [Déclaration de l'index de la propriété](../dotnet/property-index-declaration.md).  
  
## Opérateurs surchargés  
 Syntaxe de la surcharge d'opérateur en Extensions managées :  
  
```  
public __gc __sealed class Vector {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    op_Equality( const Vector*, const Vector* );  
   static Vector* op_Division( const Vector*, double );  
};  
  
int main() {  
   Vector *pa = new Vector( 0.231, 2.4745, 0.023 );  
   Vector *pb = new Vector( 1.475, 4.8916, -1.23 );   
  
   Vector *pc = Vector::op_Division( pa, 4.8916 );  
  
   if ( Vector::op_Equality( pa, pc ))  
      ;  
}  
```  
  
 Nouvelle syntaxe de la surcharge d'opérateur :  
  
```  
public ref class Vector sealed {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    operator ==( const Vector^, const Vector^ );  
   static Vector^ operator /( const Vector^, double );  
};  
  
int main() {  
   Vector^ pa = gcnew Vector( 0.231, 2.4745, 0.023 );  
   Vector^ pb = gcnew Vector( 1.475, 4.8916, -1.23 );  
  
   Vector^ pc = pa / 4.8916;  
   if ( pc == pa )  
      ;  
}  
```  
  
 Pour plus d'informations, consultez [Opérateurs surchargés](../dotnet/overloaded-operators.md).  
  
## Opérateurs de conversion  
 Syntaxe de l'opérateur de conversion en Extensions managées :  
  
```  
__gc struct MyDouble {  
   static MyDouble* op_Implicit( int i );   
   static int op_Explicit( MyDouble* val );  
   static String* op_Explicit( MyDouble* val );   
};  
```  
  
 Nouvelle syntaxe de l'opérateur de conversion :  
  
```  
ref struct MyDouble {  
public:  
   static operator MyDouble^ ( int i );  
   static explicit operator int ( MyDouble^ val );  
   static explicit operator String^ ( MyDouble^ val );  
};  
```  
  
 Pour plus d'informations, consultez [Modifications apportées aux opérateurs de conversion](../dotnet/changes-to-conversion-operators.md).  
  
## Substitution explicite d'un membre d'interface  
 Syntaxe de la substitution explicite en Extensions managées :  
  
```  
public __gc class R : public ICloneable {  
   // to be used through ICloneable  
   Object* ICloneable::Clone();  
  
   // to be used through an R  
   R* Clone();  
};  
```  
  
 Nouvelle syntaxe de la substitution explicite :  
  
```  
public ref class R : public ICloneable {  
   // to be used through ICloneable  
   virtual Object^ InterfaceClone() = ICloneable::Clone;  
  
   // to be used through an R   
   virtual R^ Clone();  
};  
```  
  
 Pour plus d'informations, consultez [Substitution explicite d'un membre d'interface](../dotnet/explicit-override-of-an-interface-member.md).  
  
## Fonctions virtuelles privées  
 Syntaxe des fonctions virtuelles privées en Extensions managées :  
  
```  
__gc class Base {  
private:  
   // inaccessible to a derived class  
   virtual void g();   
};  
  
__gc class Derived : public Base {  
public:  
   // ok: g() overrides Base::g()  
   virtual void g();  
};  
```  
  
 Nouvelle syntaxe des fonctions virtuelles privées  
  
```  
ref class Base {  
private:  
   // inaccessible to a derived class  
   virtual void g();   
};  
  
ref class Derived : public Base {  
public:  
   // error: cannot override: Base::g() is inaccessible  
   virtual void g() override;  
};  
```  
  
 Pour plus d'informations, consultez [Fonctions virtuelles privées](../dotnet/private-virtual-functions.md).  
  
## Type Enum du CLR  
 Syntaxe des enums en Extensions managées :  
  
```  
__value enum e1 { fail, pass };  
public __value enum e2 : unsigned short  {   
   not_ok = 1024,   
   maybe, ok = 2048   
};    
```  
  
 Nouvelle syntaxe des enums :  
  
```  
enum class e1 { fail, pass };  
public enum class e2 : unsigned short {   
   not_ok = 1024,  
   maybe, ok = 2048   
};  
```  
  
 Outre cette légère modification syntaxique, le comportement du type d'enum du CLR a été modifié de plusieurs manières :  
  
-   La déclaration anticipée d'un enum du CLR n'est plus prise en charge.  
  
-   La résolution de la surcharge entre les types arithmétiques intégrés et la hiérarchie des classes Objet a été inversée entre Extensions managées et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  Un des effets secondaires est que les enums du CLR ne sont plus convertis implicitement en types arithmétiques.  
  
-   Dans la nouvelle syntaxe, un enum du CLR conserve sa propre portée, ce qui n'est pas le cas en Extensions managées.  Auparavant, les énumérateurs étaient visibles dans la portée contenant l'enum ; dorénavant, ils sont encapsulés dans la portée de l'enum.  
  
 Pour plus d'informations, consultez [Type Enum du CLR](../dotnet/clr-enum-type.md).  
  
## Suppression du mot clé \_\_box  
 Syntaxe de la conversion boxing en Extensions managées :  
  
```  
Object *o = __box( 1024 ); // explicit boxing  
```  
  
 Nouvelle syntaxe de la conversion boxing :  
  
```  
Object ^o = 1024; // implicit boxing  
```  
  
 Pour plus d'informations, consultez [Handle de suivi d'une valeur boxed](../dotnet/a-tracking-handle-to-a-boxed-value.md).  
  
## Pointeur épingle  
 Syntaxe du pointeur épingle en Extensions managées :  
  
```  
__gc struct H { int j; };  
  
int main() {  
   H * h = new H;  
   int __pin * k = & h -> j;  
};  
```  
  
 Nouvelle syntaxe du pointeur épingle :  
  
```  
ref struct H { int j; };  
  
int main() {  
   H^ h = gcnew H;  
   pin_ptr<int> k = &h->j;  
}  
```  
  
 Pour plus d'informations, consultez [Sémantique de type valeur](../dotnet/value-type-semantics.md).  
  
## Le mot clé \_\_typeof devient typeid  
 Syntaxe de typeof en Extensions managées :  
  
```  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 Nouvelle syntaxe de typeid :  
  
```  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
 Pour plus d'informations, consultez [typeof va à T::typeid](../dotnet/typeof-goes-to-t-typeid.md).  
  
## Voir aussi  
 [Initiation à la migration de C\+\+\/CLI](../dotnet/cpp-cli-migration-primer.md)   
 [\(NOTINBUILD\)Managed Extensions for C\+\+ Syntax Upgrade Checklist](http://msdn.microsoft.com/fr-fr/edbded88-7ef3-4757-bd9d-b8f48ac2aada)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)