---
title: "User-Defined Attributes  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "metadata, extending"
  - "custom attributes, extending metadata"
ms.assetid: 98b29048-a3ea-4698-8441-f149cdaec9fb
caps.latest.revision: 27
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# User-Defined Attributes  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les attributs personnalisés permettent d'étendre les métadonnées d'une interface, d'une classe ou d'une structure, d'une méthode, d'un paramètre, ou d'une énumération.  
  
## Tous les runtimes  
 Tous les attributs personnalisés de support de délais d'exécution.  
  
## Windows Runtime  
 Les attributs de C\+\+\/CX ne prennent en charge que les propriétés, mais ne déplace pas les constructeurs ou les méthodes.  
  
### Remarques  
  
### Conditions requises  
 Option du compilateur : **\/ZW**  
  
## Common Language Runtime  
 Les attributs personnalisés vous permettent d'étendre les métadonnées d'un élément géré.  Pour plus d'informations, consultez [Attributs](../Topic/Extending%20Metadata%20Using%20Attributes.md).  
  
### Remarques  
 Les informations et la syntaxe présentés dans cette rubrique sont censées remplacer les informations présentées dans [attribute](../windows/attribute.md).  
  
 Vous pouvez définir un attribut personnalisé en définissant le type et le <xref:System.Attribute> à une classe de base pour le type et en appliquant éventuellement l'attribut <xref:System.AttributeUsageAttribute>.  
  
 Par exemple, dans Microsoft Transaction \(MTS\) Server 1,0, le comportement par rapport aux transactions, à la synchronization, à l'équilibrage de charge, etc. a été spécifié par GUID personnalisé inséré dans la bibliothèque de types à l'aide de l'attribut personnalisé à ODL.  Par conséquent, un client à un serveur de MTS peut déterminer ses caractéristiques en lisant la bibliothèque de types.  Dans le.NET Framework, l'analogue de la bibliothèque de types sont des métadonnées, et l'analogue de l'attribut personnalisé à ODL sont des attributs personnalisés.  En outre, lire la bibliothèque de types est analogue à utiliser la réflexion sur les types.  
  
 Pour plus d'informations, consultez  
  
-   [Attribute Targets](../windows/attribute-targets-cpp-component-extensions.md)  
  
-   [Attribute Parameter Types](../windows/attribute-parameter-types-cpp-component-extensions.md)  
  
 Pour plus d'informations sur la signature d'assemblys dans des projets Visual C\+\+, consultez [Assemblys de nom fort \(signature d'assembly\)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
### Conditions requises  
 Option du compilateur : **\/clr**  
  
### Exemples  
 **Exemple**  
  
 L'exemple suivant montre comment définir un attribut personnalisé:  
  
```cpp  
// user_defined_attributes.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::All)]  
ref struct Attr : public Attribute {  
   Attr(bool i){}  
   Attr(){}  
};  
  
[Attr]  
ref class MyClass {};  
```  
  
 **Exemple**  
  
 L'exemple suivant illustre quelques fonctionnalités importantes des attributs personnalisés.  Par exemple, cet exemple illustre une utilisation courante des attributs personnalisés : instanciation d'un serveur qui peut amplement décrire les clients.  
  
```cpp  
// extending_metadata_b.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
  
public enum class Access { Read, Write, Execute };  
  
// Defining the Job attribute:  
[AttributeUsage(AttributeTargets::Class, AllowMultiple=true )]  
public ref class Job : Attribute {  
public:  
   property int Priority {  
      void set( int value ) { m_Priority = value; }  
      int get() { return m_Priority; }  
   }  
  
   // You can overload constructors to specify Job attribute in different ways  
   Job() { m_Access = Access::Read; }  
   Job( Access a ) { m_Access = a; }  
   Access m_Access;  
  
protected:  
   int m_Priority;  
};  
  
interface struct IService {  
   void Run();  
};  
  
   // Using the Job attribute:  
   // Here we specify that QueryService is to be read only with a priority of 2.  
   // To prevent namespace collisions, all custom attributes implicitly   
   // end with "Attribute".   
  
[Job( Access::Read, Priority=2 )]  
ref struct QueryService : public IService {  
   virtual void Run() {}  
};  
  
// Because we said AllowMultiple=true, we can add multiple attributes   
[Job(Access::Read, Priority=1)]  
[Job(Access::Write, Priority=3)]  
ref struct StatsGenerator : public IService {  
   virtual void Run( ) {}  
};  
  
int main() {  
   IService ^ pIS;  
   QueryService ^ pQS = gcnew QueryService;  
   StatsGenerator ^ pSG = gcnew StatsGenerator;  
  
   //  use QueryService  
   pIS = safe_cast<IService ^>( pQS );  
  
   // use StatsGenerator  
   pIS = safe_cast<IService ^>( pSG );  
  
   // Reflection  
   MemberInfo ^ pMI = pIS->GetType();  
   array <Object ^ > ^ pObjs = pMI->GetCustomAttributes(false);  
  
   // We can now quickly and easily view custom attributes for an   
   // Object through Reflection */  
   for( int i = 0; i < pObjs->Length; i++ ) {  
      Console::Write("Service Priority = ");  
      Console::WriteLine(static_cast<Job^>(pObjs[i])->Priority);  
      Console::Write("Service Access = ");  
      Console::WriteLine(static_cast<Job^>(pObjs[i])->m_Access);  
   }  
}  
```  
  
 **Sortie**  
  
  **Priorité de service \= 0**  
 **Service Access \= écriture**  
 **Priorité de service \= 3**  
 **Service Access \= écriture**  
 **Priorité de service \= 1**  
 **Service Access \= lecture** **Exemple**  
  
 Le type d'Object^ remplace le type de données variant.  L'exemple suivant définit un attribut personnalisé qui prend un tableau Object^ comme paramètres.  
  
 Les arguments d'attribut doivent être des constantes de compilation ; dans la plupart des cas, ils doivent être des littéraux constants.  
  
 Consultez [typeid](../windows/typeid-cpp-component-extensions.md) pour plus d'informations sur la façon d'obtenir la valeur de System::Type d'un bloc d'attribut personnalisé.  
  
```cpp  
// extending_metadata_e.cpp  
// compile with: /clr /c  
using namespace System;  
[AttributeUsage(AttributeTargets::Class | AttributeTargets::Method)]  
public ref class AnotherAttr : public Attribute {  
public:  
   AnotherAttr(array<Object^>^) {}  
   array<Object^>^ var1;  
};  
  
// applying the attribute  
[ AnotherAttr( gcnew array<Object ^> { 3.14159, "pi" }, var1 = gcnew array<Object ^> { "a", "b" } ) ]  
public ref class SomeClass {};  
```  
  
 **Exemple**  
  
 Le runtime nécessite que la partie publique de la classe d'attributs personnalisée doit être sérialisable.  En créant des attributs personnalisés, les arguments nommés de l'attribut personnalisé sont limités aux constantes de compilation.  \(Pensez à utiliser comme séquence de bits ajoutés à votre présentation de la classe dans les métadonnées.\)  
  
```cpp  
// extending_metadata_f.cpp  
// compile with: /clr /c  
using namespace System;  
ref struct abc {};  
  
[AttributeUsage( AttributeTargets::All )]  
ref struct A : Attribute {  
   A( Type^ ) {}  
   A( String ^ ) {}  
   A( int ) {}  
};  
  
[A( abc::typeid )]  
ref struct B {};  
```  
  
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)