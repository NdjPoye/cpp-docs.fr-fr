---
title: "Windows Runtime and Managed Templates (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "templates, with CLR types"
ms.assetid: cf59d16b-5514-448b-9a95-e0b4fcb616a6
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Runtime and Managed Templates (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les modèles vous permettent de définir un prototype de windows runtime ou de type CLR au moment de l'exécution, puis instancient des variantes de ce type à l'aide de différents paramètres de type de modèle.  
  
## Tous les runtimes  
 Vous pouvez créer des modèles de valeur ou de types référence.  Pour plus d'informations sur la création de types de reference ou de valeur, consultez [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Pour plus d'informations sur les modèles de classes C\+\+ standards, consultez [Modèles de classe](../cpp/class-templates.md).  
  
## Windows Runtime  
 \(Aucune note de cette fonctionnalité de langage ne s'applique qu'au Windows Runtime.\)  
  
### Conditions requises  
 Option du compilateur : **\/ZW**  
  
## Common Language Runtime  
 Il existe des limitations pour créer des modèles de classe de types managés, qui sont illustrés dans les exemples de code suivants.  
  
### Conditions requises  
 Option du compilateur : **\/clr**  
  
### Exemples  
 **Exemple**  
  
 Il est possible d'instancier un type générique avec un paramètre de modèle de type managé, mais vous ne pouvez pas instancier un modèle managé avec un paramètre de modèle générique de type.  Cela est dû au fait que les types génériques sont résolus au moment de l'exécution.  Pour plus d'informations, consultez [Generics and Templates \(Visual C\+\+\)](../windows/generics-and-templates-visual-cpp.md).  
  
```cpp  
// managed_templates.cpp  
// compile with: /clr /c  
  
generic<class T>   
ref class R;   
  
template<class T>   
ref class Z {  
   // Instantiate a generic with a template parameter.  
   R<T>^ r;    // OK  
};  
  
generic<class T>   
ref class R {  
   // Cannot instantiate a template with a generic parameter.  
   Z<T>^ z;   // C3231  
};  
```  
  
 **Exemple**  
  
 Un type ou une fonction générique ne peut pas être imbriquée dans un modèle managé.  
  
```cpp  
// managed_templates_2.cpp  
// compile with: /clr /c  
  
template<class T> public ref class R {  
   generic<class T> ref class W {};   // C2959  
};  
```  
  
 **Exemple**  
  
 Vous ne pouvez pas accéder à des modèles définis dans un assembly référencé avec la syntaxe de données C\+\+\/CLI, mais vous pouvez utiliser la réflexion.  Si un modèle n'est pas instancié, il n'est pas émis dans les métadonnées.  Si un modèle est instancié, seules les fonctions membres référencées apparaissent dans les métadonnées.  
  
```cpp  
// managed_templates_3.cpp  
// compile with: /clr  
  
// Will not appear in metadata.  
template<class T> public ref class A {};  
  
// Will appear in metadata as a specialized type.  
template<class T> public ref class R {  
public:  
   // Test is referenced, will appear in metadata  
   void Test() {}  
  
   // Test2 is not referenced, will not appear in metadata  
   void Test2() {}  
};  
  
// Will appear in metadata.  
generic<class T> public ref class G { };  
  
public ref class S { };  
  
int main() {  
   R<int>^ r = gcnew R<int>;  
   r->Test();  
}  
```  
  
 **Exemple**  
  
 Vous pouvez modifier le modificateur managé d'une classe d'une spécialisation partielle ou la spécialisation explicite d'un modèle de la classe.  
  
```cpp  
// managed_templates_4.cpp  
// compile with: /clr /c  
  
// class template  
// ref class  
template <class T>  
ref class A {};  
  
// partial template specialization  
// value type  
template <class T>  
value class A <T *> {};  
  
// partial template specialization  
// interface  
template <class T>   
interface class A<T%> {};  
  
// explicit template specialization  
// native class  
template <>  
class A <int> {};  
  
```  
  
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)