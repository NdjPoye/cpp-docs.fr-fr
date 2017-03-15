---
title: "safe_cast (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "safe_cast"
  - "safe_cast_cpp"
  - "stdcli::language::safe_cast"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "safe_cast keyword [C++]"
ms.assetid: 4fa688bf-a8ec-49bc-a4c5-f48134efa4f7
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# safe_cast (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'opération `safe_cast` retourne l'expression spécifiée en tant que type spécifié, en cas de réussite ; sinon, lève une exception `InvalidCastException`.  
  
## Tous les runtimes  
 \(Aucune remarque pour cette fonctionnalité de langage ne s'applique à tous les runtimes.\)  
  
### Syntaxe  
  
```cpp  
  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### Paramètres  
  
### Notes  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 `safe_cast` vous permet de modifier le type d'une expression spécifiée.  Dans les situations où vous vous attendez à ce qu'une variable ou un paramètre soit convertible en un certain type, vous pouvez utiliser safe\_cast sans bloc try\-catch pour détecter les erreurs de programmation pendant le développement.  Pour plus d'informations, consultez [Effectuer un cast \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh755802.aspx).  
  
### Syntaxe  
  
```cpp  
  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### Paramètres  
 *id du type*  
 Type vers lequel convertir une *expression*.  Handle vers un type référence ou valeur, type valeur ou référence de suivi à un type référence ou valeur.  
  
 *expression*  
 Expression qui s'évalue en handle vers un type référence ou type valeur, type valeur ou référence de suivi vers un type référence ou valeur.  
  
### Notes  
 `safe_cast` lève une exception `InvalidCastException` la conversion de l'*expression* dans le type spécifié par *id de type* n'est pas possible.  Pour intercepter `InvalidCastException`, spécifiez l'option du compilateur [\/EH \(Modèle de gestion des exceptions\)](../build/reference/eh-exception-handling-model.md) et utilisez une instruction try\/catch.  
  
### Spécifications  
 Option du compilateur : **\/ZW**  
  
### Exemples  
 **Exemple**  
  
 L'exemple de code suivant illustre l'utilisation de `safe_cast` avec [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
```cpp#  
// safe_cast_ZW.cpp  
// compile with: /ZW /EHsc  
  
using namespace default;  
using namespace Platform;  
  
interface class I1 {};  
interface class I2 {};  
interface class I3 {};  
  
ref class X : public I1, public I2 {};  
  
int main(Array<String^>^ args) {  
   I1^ i1 = ref new X;  
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X  
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead  
   try {  
      I3^ i4 = safe_cast<I3^>(i1);   // Fails because i1 is not derived from I3.  
   }   
   catch(InvalidCastException^ ic) {  
     wprintf(L"Caught expected exception: %s\n", ic->Message);  
   }  
}  
```  
  
 **Sortie**  
  
  **Exception attendue interceptée : InvalidCastException**   
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 `safe_cast` vous permet de modifier le type d'une expression et de générer du code MSIL vérifiable.  
  
### Syntaxe  
  
```cpp  
  
[cli]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### Paramètres  
 *id du type*  
 Handle vers un type référence ou valeur, type valeur ou référence de suivi à un type référence ou valeur.  
  
 *expression*  
 Expression qui s'évalue en handle vers un type référence ou type valeur, type valeur ou référence de suivi vers un type référence ou valeur.  
  
### Notes  
 L'expression `safe_cast<`*id de type*`>(`*expression*`)` convertit l'expression d'opérande en objet de type id de type.  
  
 Le compilateur accepte un [static\_cast](../cpp/static-cast-operator.md) à la plupart des emplacements auxquels il n'accepte un `safe_cast`.  Toutefois, `safe_cast` garantit la production de code MSIL vérifiable, alors qu'un `static_cast` peut produire du code MSIL non vérifiable.  Voir [Code pur et vérifiable](../dotnet/pure-and-verifiable-code-cpp-cli.md) et [Peverify.exe \(PEVerify Tool\)](../Topic/Peverify.exe%20\(PEVerify%20Tool\).md) pour plus d'informations sur le code vérifiable.  
  
 Comme `static_cast`, `safe_cast` appelle des conversions définies par l'utilisateur.  
  
 Pour plus d'informations sur les casts, consultez [Opérateurs de casting](../cpp/casting-operators.md).  
  
 `safe_cast` n'applique pas de **const\_cast** \(rejet de **const**\).  
  
 `safe_cast` est dans l'espace de noms cli.  Consultez [Platform, default, and cli Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) pour plus d'informations.  
  
 Pour plus d'informations sur **safe\_cas**t, consultez :  
  
-   [C\-Style Casts with \/clr \(C\+\+\/CLI\)](../windows/c-style-casts-with-clr-cpp-cli.md)  
  
-   [Comment : utiliser safe\_cast dans C\+\+\/CLI](../dotnet/how-to-use-safe-cast-in-cpp-cli.md)  
  
-   [Comment : utiliser un cast aval avec safe\_cast](../misc/how-to-downcast-with-safe-cast.md)  
  
-   [Comment : utiliser safe\_cast et des types génériques](../misc/how-to-use-safe-cast-and-generic-types.md)  
  
-   [Comment : utiliser safe\_cast et des conversions définies par l'utilisateur](../misc/how-to-use-safe-cast-and-user-defined-conversions.md)  
  
-   [Comment : utiliser safe\_cast et boxing](../misc/how-to-use-safe-cast-and-boxing.md)  
  
-   [Comment : utiliser safe\_cast et unboxing](../misc/how-to-use-safe-cast-and-unboxing.md)  
  
### Spécifications  
 Option du compilateur : **\/clr**  
  
### Exemples  
 **Exemple**  
  
 Les casts entre types d'interface non liés constituent un exemple où le compilateur n'accepte pas un `static_cast` mais accepte un `safe_cast`.  Avec `safe_cast`, le compilateur n'émet pas d'erreur de conversion et effectue une vérification au moment de l'exécution si le cast est possible.  
  
```cpp  
// safe_cast.cpp  
// compile with: /clr  
using namespace System;  
  
interface class I1 {};  
interface class I2 {};  
interface class I3 {};  
  
ref class X : public I1, public I2 {};  
  
int main() {  
   I1^ i1 = gcnew X;  
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X  
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead  
   try {  
      I3^ i4 = safe_cast<I3^>(i1);   // fail at runtime, no common type  
   }   
   catch(InvalidCastException^) {  
      Console::WriteLine("Caught expected exception");  
   }  
}  
```  
  
 **Sortie**  
  
  **Exception attendue interceptée**   
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)