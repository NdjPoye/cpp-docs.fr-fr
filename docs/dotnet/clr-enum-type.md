---
title: "Type Enum du CLR | Microsoft Docs"
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
  - "classe enum (mot clé C++)"
  - "structure enum (mot clé C++)"
  - "portée, d'enum CLR"
ms.assetid: 4541d952-97bb-4e35-a7f8-d14f5f6a6606
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Type Enum du CLR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La déclaration et le comportement des enums ont été modifiés entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 La déclaration d'enum en Extensions managées est précédée du mot clé `__value`.  L'idée ici est de distinguer l'enum natif de l'enum du CLR, lequel est dérivé de `System::ValueType`, tout en suggérant des fonctionnalités analogues.  Par exemple :  
  
```  
__value enum e1 { fail, pass };  
public __value enum e2 : unsigned short  {   
   not_ok = 1024,   
   maybe, ok = 2048   
};  
```  
  
 La nouvelle syntaxe résout le problème de la distinction entre enums natifs et enums du CLR en soulignant la nature de classe du dernier plutôt que ses racines de type valeur.  Comme tel, le mot clé `__value` est ignoré et remplacé par la paire de mots clés espacés `enum class`.  Cela fournit une symétrie de paires de mots clés vis\-à\-vis des déclarations de classes de référence, de valeur et d'interface :  
  
```  
enum class ec;  
value class vc;  
ref class rc;  
interface class ic;  
```  
  
 La traduction de la paire d'énumération `e1` et `e2` dans la nouvelle syntaxe ressemble à ceci :  
  
```  
enum class e1 { fail, pass };  
public enum class e2 : unsigned short {   
   not_ok = 1024,  
   maybe, ok = 2048   
};  
```  
  
 Outre cette légère modification syntaxique, le comportement du type d'enum du CLR a été modifié de plusieurs manières :  
  
-   La déclaration anticipée d'un enum du CLR n'est plus prise en charge.  Il n'y a aucun mappage.  Elle est simplement signalée comme erreur de compilation.  
  
```  
__value enum status; // Managed Extensions: ok  
enum class status;   // new syntax: error  
```  
  
-   La résolution de la surcharge entre les types arithmétiques intégrés et la hiérarchie des classes `Object` a été inversée entre les deux versions du langage \!  Un des effets secondaires est que les enums du CLR ne sont plus convertis implicitement en types arithmétiques.  
  
-   Dans la nouvelle syntaxe, un enum du CLR conserve sa propre portée, ce qui n'est pas le cas en Extensions managées.  Auparavant, les énumérateurs étaient visibles dans la portée contenant l'enum.  Maintenant, les énumérateurs sont encapsulés dans la portée de l'enum.  
  
## Les enums du CLR sont une sorte d'objet  
 Prenons le fragment de code suivant :  
  
```  
__value enum status { fail, pass };  
  
void f( Object* ){ Console::WriteLine("f(Object)\n"); }  
void f( int ){ Console::WriteLine("f(int)\n"); }  
  
int main()  
{  
   status rslt = fail;  
  
   f( rslt ); // which f is invoked?  
}  
```  
  
 Pour le programmeur en C\+\+ natif, la réponse naturelle à la question consistant à savoir quelle instance de `f()` surchargée appeler est celle de `f(int)`.  Un enum est une constante intégrale symbolique et il participe aux promotions intégrales standard qui prennent ici la priorité.  D'ailleurs, en Extensions managées, c'était l'instance sur laquelle l'appel résolvait.  Cela provoquait un certain nombre de surprises \- non lorsqu'ils étaient utilisés dans un état d'esprit C\+\+ natif \- mais lorsque nous avions besoin qu'ils interagissent avec l'infrastructure de la BCL \(bibliothèque de classes de base\) existante, dans laquelle un `Enum` est une classe dérivée indirectement de `Object`.  Dans la conception du langage [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)], l'instance de `f()` appelée est celle de `f(Object^)`.  
  
 Le mode choisi par [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] pour faire appliquer ceci consiste à ne pas prendre en charge de conversions implicites entre un type d'enum du CLR et les types arithmétiques.  Cela signifie que toute assignation d'un objet d'un type d'enum du CLR à un type arithmétique requerra un cast explicite.  Si bien que, par exemple, étant donné :  
  
```  
void f( int );  
```  
  
 comme méthode non\-surchargée, en Extensions managées, l'appel  
  
```  
f( rslt ); // ok: Managed Extensions; error: new syntax  
```  
  
 est correct, et la valeur contenue dans `rslt` est implicitement convertie en une valeur entière.  Dans [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)], cet appel échoue lors de la compilation.  Pour le traduire correctement, nous devons insérer un opérateur de conversion :  
  
```  
f( safe_cast<int>( rslt )); // ok: new syntax  
```  
  
## La portée du type d'enum du CLR  
 L'une des modifications intervenues entre le langage C et C\+\+ a été l'ajout, dans C\+\+, de la portée au sein du dispositif de struct.  En C, un struct n'est qu'un agrégat de données sans prise en charge d'une interface ou d'une portée associée.  Cela a représenté une modification radicale et a engendré un sujet de controverse pour de nombreux utilisateurs novices en C\+\+ qui venaient du langage C.  La relation entre l'enum natif et l'enum du CLR est du même genre.  
  
 En Extensions managées, une tentative a été faite pour définir des noms injectés faiblement pour les énumérateurs d'un enum du CLR afin de simuler l'absence de portée dans l'enum natif.  Elle n'a pas abouti.  En effet, cela pousse les énumérateurs à se répandre dans l'espace de noms global, avec pour résultat des collisions de noms difficiles à gérer.  Dans la nouvelle syntaxe, nous nous sommes conformés aux autres langages du CLR en prenant en charge les portées dans l'enum du CLR.  
  
 Cela signifie que toute utilisation non qualifiée d'un énumérateur d'un enum du CLR ne sera pas reconnue par la nouvelle syntaxe.  Prenons un exemple concret.  
  
```  
// Managed Extensions supporting weak injection  
__gc class XDCMake {  
public:  
   __value enum _recognizerEnum {   
      UNDEFINED,  
      OPTION_USAGE,   
      XDC0001_ERR_PATH_DOES_NOT_EXIST = 1,  
      XDC0002_ERR_CANNOT_WRITE_TO = 2,  
      XDC0003_ERR_INCLUDE_TAGS_NOT_SUPPORTED = 3,  
      XDC0004_WRN_XML_LOAD_FAILURE = 4,  
      XDC0006_WRN_NONEXISTENT_FILES = 6,  
   };  
  
   ListDictionary* optionList;  
   ListDictionary* itagList;  
  
   XDCMake() {  
      optionList = new ListDictionary;  
  
      // here are the problems …  
      optionList->Add(S"?", __box(OPTION_USAGE)); // (1)  
      optionList->Add(S"help", __box(OPTION_USAGE)); // (2)  
  
      itagList = new ListDictionary;  
      itagList->Add(S"returns",   
         __box(XDC0004_WRN_XML_LOAD_FAILURE)); // (3)  
   }  
};  
```  
  
 Chacune des trois utilisations non qualifiées des noms d'énumérateur \(`(1)`, `(2)` et `(3)`\) devra être qualifié dans la traduction vers la nouvelle syntaxe afin que le code source puisse compiler.  Voici une traduction correcte du code source d'origine :  
  
```  
ref class XDCMake {  
public:  
   enum class _recognizerEnum {  
      UNDEFINED, OPTION_USAGE,   
      XDC0001_ERR_PATH_DOES_NOT_EXIST = 1,  
      XDC0002_ERR_CANNOT_WRITE_TO = 2,  
      XDC0003_ERR_INCLUDE_TAGS_NOT_SUPPORTED = 3,  
      XDC0004_WRN_XML_LOAD_FAILURE = 4,  
      XDC0006_WRN_NONEXISTENT_FILES = 6  
   };  
  
   ListDictionary^ optionList;  
   ListDictionary^ itagList;  
  
   XDCMake() {  
      optionList = gcnew ListDictionary;  
      optionList->Add("?",_recognizerEnum::OPTION_USAGE); // (1)  
      optionList->Add("help",_recognizerEnum::OPTION_USAGE); //(2)  
      itagList = gcnew ListDictionary;  
      itagList->Add( "returns",   
         _recognizerEnum::XDC0004_WRN_XML_LOAD_FAILURE); //(3)  
   }  
};  
```  
  
 Cela modifie la stratégie de conception entre un enum natif et un enum du CLR.  Avec un enum du CLR conservant une portée associée dans [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)], il n'est ni nécessaire ni efficace d'encapsuler la déclaration de l'enum dans une classe.  Cet idiome a évolué à l'époque de cfront 2.0 dans les Laboratoires Bell dans le but de résoudre également le problème de pollution du nom global.  
  
 Dans la version bêta d'origine de la nouvelle bibliothèque iostream, conçue par Jerry Schwarz dans les Laboratoires Bell, Jerry n'avait pas encapsulé tous les enums associés définis pour la bibliothèque, et les énumérateurs courants, tels que `read`, `write`, `append`, etc., rendaient presque impossible pour les utilisateurs la compilation de leur code existant.  Une solution aurait été de mutiler les noms, tel que `io_read`, `io_write`, etc. Une autre solution aurait été de modifier le langage en ajoutant de la portée à une énumération, mais ce n'était pas possible à l'époque.  La solution intermédiaire a été d'encapsuler l'enum dans la classe, ou la hiérarchie de classes, solution dans laquelle le nom de balise et les énumérateurs de l'enum remplissent la portée de la classe englobante.\) C'est ainsi que la motivation poussant à placer des enums dans des classes, tout au moins à l'origine, n'a pas été d'ordre philosophique, mais a représenté une réponse pratique au problème global de la pollution de l'espace de noms.  
  
 Avec l'enum de [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)], l'avantage majeur de l'encapsulation d'un enum dans une classe disparaît.  En réalité, si vous regardez les espaces de noms `System`, vous verrez qu'enums, classes et interfaces habitent tous le même espace de déclaration.  
  
## Voir aussi  
 [Types valeur et leurs comportements \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [enum, classe](../windows/enum-class-cpp-component-extensions.md)