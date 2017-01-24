---
title: "La liaison Static Const Int n&#39;est plus litt&#233;rale | Microsoft Docs"
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
  - "constantes, déclarer"
  - "constante intégrale (expressions)"
  - "attribut littéral (C++)"
ms.assetid: d2a5e3d2-ffb0-4b61-8114-bec5993a1195
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# La liaison Static Const Int n&#39;est plus litt&#233;rale
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La déclaration d'un membre constant d'une classe a été modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 Bien que les membres intégraux `static const` soient encore pris en charge, leur attribut de chaînage a été modifié.  Leur précédent attribut de chaînage est désormais porté par un membre intégral littéral.  Par exemple, considérons la classe Extensions managées suivante :  
  
```  
public __gc class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 Elle génère pour le champ les attributs CIL sous\-jacents suivants \(notez l'attribut littéral\) :  
  
```  
.field public static literal int32   
modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 Bien qu'elle continue à compiler sous la nouvelle syntaxe :  
  
```  
public ref class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 elle n'émet plus l'attribut littéral, et par conséquent n'est pas affichée comme une constante par le runtime CLR :  
  
```  
.field public static int32 modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 Pour conserver le même attribut littéral d'un langage à l'autre, il faut transformer la déclaration en la donnée membre `literal` récemment prise en charge, comme suit,  
  
```  
public ref class Constants {  
public:  
   literal int LOG_DEBUG = 4;  
};  
```  
  
## Voir aussi  
 [Déclarations de membre dans une classe ou interface \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [literal](../windows/literal-cpp-component-extensions.md)