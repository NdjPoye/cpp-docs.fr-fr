---
title: "Platform::Metadata::RuntimeClassName | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Metadata::RuntimeClassName"
helpviewer_keywords: 
  - "RuntimeClassName"
  - "Platform::Metadata::RuntimeClassName"
ms.assetid: fdef8f85-ab94-4edd-ba50-ee0da9358ff6
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 2
---
# Platform::Metadata::RuntimeClassName
Lorsqu'une classe privée est appliquée à une définition de classe, elle assure le retour d'un nom valide à partir de la fonction GetRuntimeClassName.  
  
## Syntaxe  
  
```vb  
[Platform::Metadata::RuntimeClassName] name  
```  
  
#### Paramètres  
 name  
  
 Le nom d'un type public existant visible dans le Windows Runtime.  
  
## Notes  
 Utilisez cet attribut sur des classes ref privées pour spécifier un nom de type de runtime personnalisé et\/ou lorsque le nom existant ne répond pas aux spécifications. Spécifiez une interface publique en tant que nom, que la classe implémente.  
  
## Exemple  
 L'exemple suivant montre comment utiliser l'attribut. Dans cet exemple, le nom de type de runtime HellowWorldImpl est Test::Native::MyComponent::IHelloWorld  
  
```  
  
namespace Test  
{  
    namespace Native  
    {  
        namespace MyComponent  
        {  
            public interface class IHelloWorld  
            {  
                Platform::String^ SayHello();  
            };  
  
            private ref class HelloWorldImpl sealed :[Platform::Metadata::RuntimeClassName] IHelloWorld  
            {  
            public:  
                HelloWorldImpl();  
                virtual Platform::String^ SayHello();  
            };  
  
            Platform::String^ HelloWorldImpl::SayHello()  
            {  
                return L"Hello World!";  
            }  
        }  
    }  
}  
```  
  
## Voir aussi  
 [Platform::Metadata \(espace de noms\)](../cppcx/platform-metadata-namespace.md)