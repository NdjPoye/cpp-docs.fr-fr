---
title: "Comment&#160;: &#233;num&#233;rer des types de donn&#233;es dans des assemblys &#224; l&#39;aide de r&#233;flexion (C++/CLI) | Microsoft Docs"
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
  - "assemblys (C++)"
  - "assemblys (C++), énumérer des types de données dans"
  - "types de données (C++), énumérer"
  - "membres publics (C++)"
  - "types publics (C++)"
  - "réflection (C++), assemblys externes"
ms.assetid: c3578e6d-bb99-4599-80e1-ab795305f878
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: &#233;num&#233;rer des types de donn&#233;es dans des assemblys &#224; l&#39;aide de r&#233;flexion (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le code suivant illustre l'énumération de types et de membres publics à l'aide de <xref:System.Reflection>.  
  
 Une fois le nom d'un assembly spécifié, dans le répertoire local ou dans le GAC, le code suivant essaie d'ouvrir l'assembly et de récupérer des descriptions.  En cas de réussite, chaque type est affiché avec ses membres publics.  
  
 Notez que <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> exige qu'aucune extension de fichier ne soit utilisée.  Par conséquent, l'utilisation de "mscorlib.dll" comme argument de ligne de commande échouera, alors que l'utilisation de "mscorlib" uniquement entraînera l'affichage des types .NET Framework.  Si aucun nom d'assembly n'est fourni, ce code détecte et signale les types contenus dans l'assembly actuel \(fichier EXE résultant de ce code\).  
  
## Exemple  
  
```  
// self_reflection.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
using namespace System::Collections;  
  
public ref class ExampleType {  
public:  
   ExampleType() {}  
   void Func() {}  
};  
  
int main() {  
   String^ delimStr = " ";  
   array<Char>^ delimiter = delimStr->ToCharArray( );  
   array<String^>^ args = Environment::CommandLine->Split( delimiter );  
  
// replace "self_reflection.exe" with an assembly from either the local  
// directory or the GAC  
   Assembly^ a = Assembly::LoadFrom("self_reflection.exe");  
   Console::WriteLine(a);  
  
   int count = 0;  
   array<Type^>^ types = a->GetTypes();  
   IEnumerator^ typeIter = types->GetEnumerator();  
  
   while ( typeIter->MoveNext() ) {  
      Type^ t = dynamic_cast<Type^>(typeIter->Current);  
      Console::WriteLine("   {0}", t->ToString());  
  
      array<MemberInfo^>^ members = t->GetMembers();  
      IEnumerator^ memberIter = members->GetEnumerator();  
      while ( memberIter->MoveNext() ) {  
         MemberInfo^ mi = dynamic_cast<MemberInfo^>(memberIter->Current);  
         Console::Write("      {0}", mi->ToString( ) );  
         if (mi->MemberType == MemberTypes::Constructor)  
            Console::Write("   (constructor)");  
  
         Console::WriteLine();  
      }  
      count++;  
   }  
   Console::WriteLine("{0} types found", count);  
}  
```  
  
## Voir aussi  
 [Réflexion](../dotnet/reflection-cpp-cli.md)