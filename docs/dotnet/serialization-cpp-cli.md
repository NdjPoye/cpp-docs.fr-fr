---
title: "S&#233;rialisation (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - ".NET Framework (C++), sérialisation"
  - "code managé (C++), sérialisation"
  - "NonSerializedAttribute (classe), applications managées"
  - "SerializableAttribute (classe), applications managées"
  - "sérialisation (C++)"
  - "sérialisation (C++), à propos de la sérialisation"
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# S&#233;rialisation (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La sérialisation \(processus de stockage de l'état d'un objet ou d'un membre sur un support permanent\) des classes managées \(y compris les différents champs ou propriétés\) est prise en charge par les classes <xref:System.SerializableAttribute> et <xref:System.NonSerializedAttribute>.  
  
## Remarques  
 Appliquez l'attribut personnalisé **SerializableAttribute** à une classe managée pour sérialiser la classe entière ou appliquez\-le uniquement à des champs ou des propriétés spécifiques pour sérialiser des parties de la classe managée.  Utilisez l'attribut personnalisé **NonSerializedAttribute** pour exempter des champs ou des propriétés d'une classe managée de la sérialisation.  
  
## Exemple  
  
### Description  
 Dans l'exemple suivant, la classe `MyClass` \(et la propriété `m_nCount`\) est marquée comme étant sérialisable.  Cependant, la propriété `m_nData` n'est pas sérialisée, comme l'indique l'attribut personnalisé **NonSerialized** :  
  
### Code  
  
```  
// serialization_and_mcpp.cpp  
// compile with: /LD /clr  
using namespace System;  
  
[ Serializable ]  
public ref class MyClass {  
public:  
   int m_nCount;  
private:  
   [ NonSerialized ]  
   int m_nData;  
};  
```  
  
### Commentaires  
 Notez que les deux attributs peuvent être référencés à l'aide de leur « nom court » \(**Serializable** et **NonSerialized**\).  Ceci est expliqué plus en détails dans [Application des attributs](../Topic/Applying%20Attributes.md).  
  
## Voir aussi  
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)