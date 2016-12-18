---
title: "Traitement de fichier.Xml | Microsoft Docs"
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
  - "documentation XML, traitement de fichiers XML"
ms.assetid: e70fdeae-80ac-4872-ab24-771c5635cfbf
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Traitement de fichier.Xml
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le compilateur génère une chaîne d'identification pour chaque construction de votre code qui est placée entre balises de manière à générer de la documentation.  Pour plus d'informations, consultez l' [Commentaires de documentation recommandés de balises](../ide/recommended-tags-for-documentation-comments-visual-cpp.md).  La chaîne d'identification identifie de manière unique la construction.  Programme qui traitent le fichier .xml peut utiliser la chaîne d'ID pour identifier les métadonnées.NET Framework ou l'élément correspondantes de réflexion auxquels la documentation s'applique.  
  
 Le fichier .xml n'est pas une représentation hiérarchique de votre code, il est une liste plate avec un ID généré pour chaque élément.  
  
 Lorsqu'il génère les chaînes d'identification, le compilateur respecte les règles suivantes :  
  
-   La chaîne ne doit contenir aucun espace blanc.  
  
-   La première partie de la chaîne d'identification identifie le type de membre identifié, à l'aide d'un caractère unique suivi de deux points.  Les types de membres suivants sont utilisés :  
  
    |Caractère|Description|  
    |---------------|-----------------|  
    |N|Espace de noms<br /><br /> Vous ne pouvez pas ajouter des commentaires de documentation à un espace de noms, références cref à un espace de noms est possible.|  
    |T|type : classe, interface, struct, enum, délégué|  
    |D|typedef|  
    |F|champ|  
    |P|propriété \(y compris les indexeurs ou autres propriétés indexées\)|  
    |M|méthode \(y compris des méthodes spéciales telles que les constructeurs, les opérateurs, etc.\)|  
    |E|événement|  
    |\!|chaîne d'erreur<br /><br /> Le reste de la chaîne fournit des informations sur l'erreur.  Le compilateur Visual C\+\+ génère des informations sur l'erreur pour les liens qui ne peuvent pas être résolus.|  
  
-   La deuxième partie de la chaîne est composée du nom complet de l'élément, à partir de la racine de l'espace de noms.  Le nom de l'élément, son type englobant ou types, et espace de noms sont séparés par des points.  Si le nom de l'élément lui\-même comporte des points, ils sont remplacés par un dièse \('\#'\).  On suppose qu'aucun élément n'a un information\- signe directement dans son nom.  Par exemple, le nom qualifié complet du constructeur d' `String` est « System.String.\#ctor ».  
  
-   Pour les propriétés et méthodes, s'il existe des arguments pour la méthode, la liste des arguments figure à la suite entre parenthèses.  En l'absence d'arguments, aucune parenthèse n'est mentionnée.  Les arguments sont séparés par des virgules.  L'encodage de chaque argument correspond directement à son encodage dans une signature .NET Framework :  
  
    -   Types de base.  Les types réguliers \(ELEMENT\_TYPE\_CLASS ou ELEMENT\_TYPE\_VALUETYPE\) sont représentés par le nom complet du type.  
  
    -   Types intrinsèques \(par exemple, ELEMENT\_TYPE\_I4, ELEMENT\_TYPE\_OBJECT, ELEMENT\_TYPE\_STRING, ELEMENT\_TYPE\_TYPEDBYREF.  et ELEMENT\_TYPE\_VOID\) sont représentés comme nom qualifié complet du type complet correspondant, par exemple, de **System.Int32** ou de **System.TypedReference**.  
  
    -   ELEMENT\_TYPE\_PTR est représenté par un '\*' à la suite du type modifié.  
  
    -   ELEMENT\_TYPE\_BYREF est représenté par un '@' à la suite du type modifié.  
  
    -   ELEMENT\_TYPE\_PINNED est représenté par un '^' à la suite du type modifié.  Le compilateur Visual C\+\+ ne génère jamais faire.  
  
    -   ELEMENT\_TYPE\_CMOD\_REQ est représenté par un '&#124;' et le nom complet de la classe de modificateur, à la suite du type modifié.  Le compilateur Visual C\+\+ ne génère jamais faire.  
  
    -   ELEMENT\_TYPE\_CMOD\_OPT est représenté par un '\!' et le nom complet de la classe de modificateur, à la suite du type modifié.  
  
    -   ELEMENT\_TYPE\_SZARRAY est représenté par "\[\]" à la suite du type d'élément du tableau.  
  
    -   ELEMENT\_TYPE\_GENERICARRAY est représenté par "\[?\]" à la suite du type d'élément du tableau.  Le compilateur Visual C\+\+ ne génère jamais faire.  
  
    -   ELEMENT\_TYPE\_ARRAY est représenté par \[*limite\_inférieure*:`size`,*limite\_inférieure*:`size`\], où le nombre de virgules correspond au rang \- 1, et les limite inférieure et taille de chaque dimension, lorsqu'elles sont connues, sont représentées sous forme décimale.  Lorsqu'une limite inférieure ou une taille n'est pas spécifiée, elle est seulement omise.  Si la limite inférieure et la taille d'une dimension particulière sont omises, le signe ':' est également omis.  Par exemple, un tableau à 2 dimensions avec des limites inférieures égales à 1, mais sans tailles spécifiées est représenté par \[1:,1:\].  
  
    -   ELEMENT\_TYPE\_FNPTR est représenté sous la forme "\=FUNC:`type`\(*signature*\)", où `type` est le type de retour et *signature* l'argument de la méthode.  En l'absence d'arguments, les parenthèses sont omises.  Le compilateur Visual C\+\+ ne génère jamais faire.  
  
     Les composants de signature suivants ne sont pas représentés parce qu'ils ne sont jamais utilisés pour différencier les méthodes surchargées :  
  
    -   convention d'appel  
  
    -   type de retour  
  
    -   ELEMENT\_TYPE\_SENTINEL  
  
-   Pour les opérateurs de conversion uniquement, la valeur de retour de la méthode est encodée en tant que « &#124; » suivi du type de retour, comme précédemment encodé.  
  
-   Pour les types génériques, le nom du type sera suivi du caractère \` puis d'un nombre qui indique le nombre de paramètres de type générique.  Par exemple :  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
     Pour un type défini comme `public class MyClass\<T, U>`.  
  
     Pour les méthodes qui prennent des types génériques comme paramètres, les paramètres de type générique sont spécifiés comme des nombres précédés de caractères \` \(par exemple \`0, \`1\).  Chaque nombre représente une notation de tableau de base zéro pour les paramètres génériques du type.  
  
## Exemple  
 Les exemples suivants montrent comment les chaînes d'ID pour une classe et ses membres seraient générés.  
  
```  
// xml_id_strings.cpp  
// compile with: /clr /doc /LD  
///   
namespace N {    
// "N:N"  
  
   /// <see cref="System" />  
   //  <see cref="N:System"/>  
   ref class X {      
   // "T:N.X"  
  
   protected:  
      ///   
      !X(){}     
      // "M:N.X.Finalize", destructor's representation in metadata  
  
   public:  
      ///   
      X() {}     
      // "M:N.X.#ctor"  
  
      ///   
      static X() {}     
      // "M:N.X.#cctor"  
  
      ///   
      X(int i) {}     
      // "M:N.X.#ctor(System.Int32)"  
  
      ///   
      ~X() {}     
      // "M:N.X.Dispose", Dispose function representation in metadata  
  
      ///   
      System::String^ q;     
      // "F:N.X.q"  
  
      ///   
      double PI;     
      // "F:N.X.PI"  
  
      ///   
      int f() { return 1; }     
      // "M:N.X.f"  
  
      ///   
      int bb(System::String ^ s, int % y, void * z) { return 1; }  
      // "M:N.X.bb(System.String,System.Int32@,System.Void*)"  
  
      ///   
      int gg(array<short> ^ array1, array< int, 2 >^ IntArray) { return 0; }   
      // "M:N.X.gg(System.Int16[], System.Int32[0:,0:])"  
  
      ///   
      static X^ operator+(X^ x, X^ xx) { return x; }  
     // "M:N.X.op_Addition(N.X,N.X)"  
  
      ///   
      property int prop;     
      // "M:N.X.prop"  
  
      ///   
      property int prop2 {     
      // "P:N.X.prop2"  
  
         ///   
         int get() { return 0; }  
         // M:N.X.get_prop2  
  
         ///   
         void set(int i) {}  
         // M:N.X.set_prop2(System.Int32)  
      }  
  
      ///   
      delegate void D(int i);   
      // "T:N.X.D"  
  
      ///   
      event D ^ d;   
      // "E:N.X.d"  
  
      ///   
      ref class Nested {};   
      // "T:N.X.Nested"  
  
      ///   
      static explicit operator System::Int32 (X x) { return 1; }   
      // "M:N.X.op_Explicit(N.X!System.Runtime.CompilerServices.IsByValue)~System.Int32"  
   };  
}  
```  
  
## Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)