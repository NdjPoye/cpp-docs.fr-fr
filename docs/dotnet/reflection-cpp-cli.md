---
title: "R&#233;flexion (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
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
  - ".NET Framework (C++), réflexion"
  - "types de données (C++), réflexion"
  - "GetType (méthode)"
  - "métadonnées, réflexion"
  - "réflection (C++)"
  - "réflection (C++), à propos de la réflexion"
  - "typeid (mot clé C++)"
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
caps.latest.revision: 24
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# R&#233;flexion (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La réflexion permet d'inspecter des types de données connus au moment de l'exécution.  Elle permet l'énumération des types de données d'un assembly donné afin de découvrir les membres d'une classe ou d'un type valeur spécifique.  Ceci est vrai que le type soit connu ou référencé au moment de la compilation ou non.  C'est donc une fonctionnalité utile pour les outils de développement et de gestion du code.  
  
 Notez que le nom d'assembly fourni est le nom fort \(consultez [Création et utilisation d'assemblys avec nom fort](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md)\), qui inclut la version, la culture et les informations sur la signature de l'assembly.  Notez également qu'il est possible de récupérer le nom de l'espace de noms dans lequel le type de données est défini, ainsi que le nom de la classe de base.  
  
 La méthode <xref:System.Object.GetType%2A> est le moyen classique d'accéder aux fonctionnalités de réflexion.  Cette méthode est fournie par [System::Object](https://msdn.microsoft.com/en-us/library/system.object.aspx), dont dérivent toutes les classes bénéficiant du garbage collection.  
  
 La réflexion sur un fichier .exe construit avec le compilateur Visual C\+\+ est autorisée si le fichier .exe est construit avec les options du compilateur **\/clr:pure** ou **\/clr:safe**.  Pour plus d'informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Rubriques de cette section :  
  
-   [Comment : implémenter une architecture de composants plug\-in à l'aide de Reflection](../dotnet/how-to-implement-a-plug-in-component-architecture-using-reflection-cpp-cli.md)  
  
-   [Comment : énumérer des types de données dans des assemblys à l'aide de Reflection](../dotnet/how-to-enumerate-data-types-in-assemblies-using-reflection-cpp-cli.md)  
  
 Pour plus d'informations, consultez [System.Reflection, espace de noms](https://msdn.microsoft.com/en-us/library/system.reflection.aspx)  
  
## Exemple  
 La méthode `GetType` retourne un pointeur vers un objet de la classe <xref:System.Type>, qui décrit le type sur lequel est basé l'objet. \(L'objet **Type** ne contient pas d'informations spécifiques à l'instance.\) L'un de ces éléments est le nom complet du type, qui peut être affiché de la façon suivante :  
  
 Notez que le nom du type inclut toute la portée dans laquelle le type est défini, y compris l'espace de noms, et qu'il est affiché selon la syntaxe .NET avec un point comme opérateur de résolution de portée.  
  
```  
// vcpp_reflection.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String ^ s = "sample string";  
   Console::WriteLine("full type name of '{0}' is '{1}'", s, s->GetType());  
}  
```  
  
  **nom complet du type de l'exemple de chaîne est « System.String »**   
## Exemple  
 Les types valeur peuvent être, eux aussi, utilisés avec la fonction `GetType`, mais ils doivent préalablement être convertis.  
  
```  
// vcpp_reflection_2.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Int32 i = 100;   
   Object ^ o = i;  
   Console::WriteLine("type of i = '{0}'", o->GetType());  
}  
```  
  
  **type de i \= 'System.Int32'**   
## Exemple  
 Comme pour la méthode `GetType`, l'opérateur [typeid](../windows/typeid-cpp-component-extensions.md) retourne un pointeur à un objet **Type**, et ce code indique donc le nom de type **System.Int32**.  L'affichage du nom des types est la fonctionnalité la plus élémentaire de la réflexion, mais une technique potentiellement plus utile consiste à inspecter ou à découvrir les valeurs valides des types énumérés.  Cela peut se faire à l'aide de la fonction statique **Enum::GetNames**, qui retourne un tableau de chaînes contenant chacune une valeur d'énumération sous forme de texte.  L'exemple suivant récupère un tableau de chaînes qui décrit les valeurs d'énumération pour l'énumération **Options** \(CLR\) et les affiche dans une boucle.  
  
 Si une quatrième option est ajoutée à l'énumération **Options**, ce code signalera la nouvelle option sans recompilation, même si l'énumération est définie dans un assembly séparé.  
  
```  
// vcpp_reflection_3.cpp  
// compile with: /clr  
using namespace System;  
  
enum class Options {   // not a native enum  
   Option1, Option2, Option3  
};  
  
int main() {  
   array<String^>^ names = Enum::GetNames(Options::typeid);  
  
   Console::WriteLine("there are {0} options in enum '{1}'",   
               names->Length, Options::typeid);  
  
   for (int i = 0 ; i < names->Length ; i++)  
      Console::WriteLine("{0}: {1}", i, names[i]);  
  
   Options o = Options::Option2;  
   Console::WriteLine("value of 'o' is {0}", o);  
}  
```  
  
  **il existe 3 options dans l'énumération "Options"**  
**0 : Option1**  
**1 : Option2**  
**2 : Option3**  
**la valeur de 'o' est Option2**   
## Exemple  
 L'objet `GetType` prend en charge des membres et des propriétés qui peuvent être utilisés pour examiner un type.  Le code suivant récupère et affiche certaines de ces informations :  
  
```  
// vcpp_reflection_4.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Console::WriteLine("type information for 'String':");  
   Type ^ t = String::typeid;  
  
   String ^ assemblyName = t->Assembly->FullName;  
   Console::WriteLine("assembly name: {0}", assemblyName);  
  
   String ^ nameSpace = t->Namespace;  
   Console::WriteLine("namespace: {0}", nameSpace);  
  
   String ^ baseType = t->BaseType->FullName;  
   Console::WriteLine("base type: {0}", baseType);  
  
   bool isArray = t->IsArray;  
   Console::WriteLine("is array: {0}", isArray);  
  
   bool isClass = t->IsClass;  
   Console::WriteLine("is class: {0}", isClass);  
}  
```  
  
  **les informations de type pour 'String' :**  
**nom de l'assembly : mscorlib, Version\=1.0.5000.0, Culture\=neutre,**   
**PublicKeyToken\=b77a5c561934e089**  
**Espace de noms : System**  
**type de base : System.Object**  
**is array: False**  
**is class: True**   
## Exemple  
 La réflexion permet aussi l'énumération des types d'un assembly et des membres d'une classe.  Pour illustrer cette fonctionnalité, définissez une classe simple :  
  
```  
// vcpp_reflection_5.cpp  
// compile with: /clr /LD  
using namespace System;  
public ref class TestClass {  
   int m_i;  
public:  
   TestClass() {}  
   void SimpleTestMember1() {}  
   String ^ SimpleMember2(String ^ s) { return s; }   
   int TestMember(int i) { return i; }  
   property int Member {  
      int get() { return m_i; }  
      void set(int i) { m_i = i; }  
   }  
};  
```  
  
## Exemple  
 Si le code ci\-dessus est compilé en une DLL appelée vcpp\_reflection\_6.dll, la réflexion peut alors servir à inspecter le contenu de cet assembly.  Ceci implique l'utilisation de la fonction d'API de réflexion statique [Assembly::Load](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.load.aspx) pour charger l'assembly.  Cette fonction retourne l'adresse d'un objet **Assembly** qui peut ensuite être interrogé au sujet des modules et des types qu'il contient.  
  
 Une fois l'assembly chargé par le système de réflexion, un tableau d'objets **Type** est récupéré à l'aide de la fonction [Assembly.GetTypes](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.gettypes.aspx).  Chaque élément du tableau contient des informations sur un type différent, bien qu'une seule classe soit définie dans ce cas.  Chaque **Type** de ce tableau est interrogé sur ses membres dans une boucle à l'aide de la fonction **Type::GetMembers**.  Cette fonction retourne un tableau d'objets **MethodInfo** contenant chacun des informations sur la fonction membre, les données membres ou la propriété du type.  
  
 Notez que la liste de méthodes contient les fonctions définies explicitement dans **TestClass** et les fonctions héritées implicitement de la classe **System::Object**.  Comme elles sont décrites en employant la syntaxe .NET au lieu de la syntaxe Visual C\+\+, les propriétés apparaissent comme les données membres sous\-jacentes auxquelles accèdent les fonctions get\/set.  Les fonctions get\/set figurent dans cette liste en tant que méthodes régulières.  La réflexion est prise en charge à travers le Common Language Runtime, et non par le compilateur Visual C\+\+.  
  
 Ce code peut servir à inspecter non seulement un assembly que vous avez défini, mais aussi des assemblys .NET.  Par exemple, si vous employez mscorlib à la place de TestAssembly, vous obtenez la liste des types et des méthodes définis dans mscorlib.dll.  
  
```  
// vcpp_reflection_6.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
using namespace System::Reflection;  
int main() {  
   Assembly ^ a = nullptr;  
   try {  
      // load assembly -- do not use file extension  
      // will look for .dll extension first  
      // then .exe with the filename  
      a = Assembly::Load("vcpp_reflection_5");  
   }  
   catch (FileNotFoundException ^ e) {  
      Console::WriteLine(e->Message);  
      return -1;  
   }  
  
   Console::WriteLine("assembly info:");  
   Console::WriteLine(a->FullName);  
   array<Type^>^ typeArray = a->GetTypes();  
  
   Console::WriteLine("type info ({0} types):", typeArray->Length);  
  
   int totalTypes = 0;  
   int totalMembers = 0;  
   for (int i = 0 ; i < typeArray->Length ; i++) {  
      // retrieve array of member descriptions  
      array<MemberInfo^>^ member = typeArray[i]->GetMembers();  
  
      Console::WriteLine("  members of {0} ({1} members):",   
      typeArray[i]->FullName, member->Length);  
      for (int j = 0 ; j < member->Length ; j++) {  
         Console::Write("       ({0})",   
         member[j]->MemberType.ToString() );  
         Console::Write("{0}  ", member[j]);  
         Console::WriteLine("");  
         totalMembers++;  
      }  
      totalTypes++;  
   }  
   Console::WriteLine("{0} total types, {1} total members",  
   totalTypes, totalMembers);  
}  
```  
  
## Voir aussi  
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)