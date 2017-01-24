---
title: "Avertissement de conformit&#233;&#160;CLS CLS00911 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CLS00911"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS00911"
ms.assetid: d1a4721a-a3a6-4de0-bc14-a0b3c5e6dd78
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# Avertissement de conformit&#233;&#160;CLS CLS00911
Les champs statiques littéraux d’une énumération auront le type de l’énumération elle\-même.  
  
 Assurez\-vous que les champs statiques littéraux d’une énumération ont le même type que l’énumération.  
  
 Pour plus d’informations sur la vérification de conformité CLS, consultez [CLS Compliant Assemblies](http://msdn.microsoft.com/fr-fr/3320b57e-ea55-4697-a17d-f509a36a3c93).  
  
 La déclaration suivante \(en langage d’assembly MSIL\) montre ce qui peut provoquer l’erreur CLS00911 :  
  
```  
.assembly extern legacy library mscorlib {} .assembly legacy library Out {} .namespace Test { .class public auto ansi sealed MyEnum1 extends [mscorlib]System.Enum { .field public specialname rtspecialname int32 value__ .field public static literal uint8 One = uint8(0x1) } // end of class MyEnum1 }  
```  
  
 En attribuant aux champs d’une énumération le même type que l’énumération, vous pouvez résoudre l’avertissement suivant :  
  
```  
.assembly extern legacy library mscorlib {} .assembly legacy library Out {} .namespace Test { .class public auto ansi sealed MyEnum1 extends [mscorlib]System.Enum { .field public specialname rtspecialname int32 value__ .field public static literal valuetype Test.MyEnum1 One = uint8(0x1) } // end of class MyEnum1 }  
```