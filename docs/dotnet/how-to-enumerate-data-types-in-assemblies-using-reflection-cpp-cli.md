---
title: "Comment : énumérer des Types de données à l’aide de la réflexion (C + c++ / CLI) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assemblies [C++], enumerating data types in
- public types [C++]
- reflection [C++], external assemblies
- assemblies [C++]
- data types [C++], enumerating
- public members [C++]
ms.assetid: c3578e6d-bb99-4599-80e1-ab795305f878
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 209124e6d4e8afa7930a4c74d2cce1acd7e279b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-enumerate-data-types-in-assemblies-using-reflection-ccli"></a>Comment : énumérer des types de données dans des assemblys à l'aide de réflexion (C++/CLI)
Le code suivant illustre l’énumération des types publics et des membres à l’aide de <xref:System.Reflection>.  
  
 Étant donné le nom d’un assembly, dans le répertoire local ou dans le GAC, le code suivant tente d’ouvrir l’assembly et de récupérer les descriptions des. En cas de réussite, chaque type est affiché avec ses membres publics.  
  
 Notez que <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> exige qu’aucune extension de fichier n’est utilisée. Par conséquent, à l’aide de « mscorlib.dll » comme un argument de ligne de commande échoue, tandis que l’utilisation de simplement « mscorlib » entraîne l’affichage des types .NET Framework. Si aucun nom de l’assembly n’est fourni, le code de détecter et signaler les types dans l’assembly actuel (obtenu à partir de ce code (EXE).  
  
## <a name="example"></a>Exemple  
  
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
  
## <a name="see-also"></a>Voir aussi  
 [Réflexion (C++-CLI)](../dotnet/reflection-cpp-cli.md)