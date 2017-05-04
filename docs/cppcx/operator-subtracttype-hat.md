---
title: "Type^, op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Type^, op&#233;rateur
Permet la conversion de [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) en `Platform::Type`.  
  
## Syntaxe  
  
```cpp  
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName)  
```  
  
## Valeur de retour  
 Retourne `Platform::Type` quand un [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) est fourni.  
  
## Notes  
 `TypeName` est la structure Windows Runtime indépendante du langage pour représenter les informations de type.[Platform::Type](../cppcx/platform-type-class.md) est spécifique à C\+\+ et ne peut pas être passé à travers l'interface binaire d'application \(ABI\). Voici une utilisation de `TypeName` dans la fonction [Navigate](http://msdn.microsoft.com/library/windows/apps/hh702394.aspx) :  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
## Exemple  
 L'exemple suivant montre comment convertir un `TypeName` en `Type`.  
  
```  
  
// Convert from Type to TypeName TypeName tn = TypeName(MainPage::typeid); // Convert back from TypeName to Type Type^ tx2 = (Type^)(tn);  
  
```  
  
## Équivalent .NET Framework  
 Projet de programmes .NET Framework `TypeName` sous la forme [System.Type](assetId:///System.Type?qualifyHint=False&amp;autoUpgrade=True).  
  
## Configuration requise  
  
## Voir aussi  
 [Windows::UI::Xaml::Interop::TypeName, opérateur](../cppcx/operator-subtractwindows-ui-xaml-interop-typename.md)   
 [Platform::Type \(classe\)](../cppcx/platform-type-class.md)