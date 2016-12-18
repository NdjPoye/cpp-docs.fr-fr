---
title: "Comment&#160;: &#233;tendre la biblioth&#232;que de marshaling | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bibliothèque de marshaling, étendre"
ms.assetid: 4c4a56d7-1d44-4118-b85f-f9686515e6e9
caps.latest.revision: 27
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: &#233;tendre la biblioth&#232;que de marshaling
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique comment étendre la bibliothèque de marshaling pour fournir plus de conversions entre des types de données.  Les utilisateurs peuvent étendre la bibliothèque de marshaling pour toutes les conversions de données non prises en charge actuellement par la bibliothèque.  
  
 Vous pouvez étendre la bibliothèque de marshaling de deux façons différentes \- avec ou sans [marshal\_context, classe](../dotnet/marshal-context-class.md).  Consultez la rubrique [Vue d'ensemble du marshaling dans C\+\+](../dotnet/overview-of-marshaling-in-cpp.md) pour déterminer si une nouvelle conversion a besoin d'un contexte.  
  
 Dans les deux cas, vous devez d'abord créer un fichier pour les nouvelles conversions de marshaling.  Le but est de préserver l'intégrité des fichiers de bibliothèque de marshaling standard.  Si vous souhaitez déplacer un projet vers un autre ordinateur ou un autre programmeur, vous devez copier le nouveau fichier marshaling avec le reste du projet.  De cette manière, l'utilisateur qui reçoit le projet sera assuré de recevoir les nouvelles conversions et n'aura pas à modifier les fichiers bibliothèque.  
  
### Pour étendre la bibliothèque Marshaling avec une conversion ne requérant pas de contexte  
  
1.  Créez un fichier pour stocker les nouvelles fonctions de marshaling, par exemple, MyMarshal.h.  
  
2.  Incluez un ou plusieurs fichiers bibliothèque marshal :  
  
    -   marshal.h pour les types de base.  
  
    -   marshal\_windows.h pour les types de données windows.  
  
    -   marshal\_cppstd.h pour les types de données STL.  
  
    -   marshal\_atl.h pour les types de données ATL.  
  
3.  Utilisez le code à la fin de ces étapes pour écrire la fonction de conversion.  Dans ce code, TO est le type vers lequel est dirigée la conversion, FROM est le type à partir duquel la conversion s'effectue et `from` est le paramètre à convertir.  
  
4.  Remplacez le commentaire à propos de la logique de conversion par du code pour convertir le paramètre `from` en un objet de type TO et retourner l'objet converti.  
  
```  
namespace msclr {  
   namespace interop {  
      template<>  
      inline TO marshal_as<TO, FROM> (const FROM& from) {  
         // Insert conversion logic here, and return a TO parameter.  
      }  
   }  
}  
```  
  
### Pour étendre la bibliothèque Marshaling avec une conversion requérant un contexte  
  
1.  Créez un fichier pour stocker les nouvelles fonctions de marshaling, par exemple, MyMarshal.h  
  
2.  Incluez un ou plusieurs fichiers bibliothèque marshal :  
  
    -   marshal.h pour les types de base.  
  
    -   marshal\_windows.h pour les types de données windows.  
  
    -   marshal\_cppstd.h pour les types de données STL.  
  
    -   marshal\_atl.h pour les types de données ATL.  
  
3.  Utilisez le code à la fin de ces étapes pour écrire la fonction de conversion.  Dans ce code, TO est le type vers lequel est dirigée la conversion, FROM est le type à partir duquel la conversion s'effectue, `toObject` est un pointeur dans lequel stocker le résultat et `fromObject` est le paramètre à convertir.  
  
4.  Remplacez le commentaire sur l'initialisation par du code pour initialiser `toPtr` à la valeur vide appropriée.  Par exemple, si c'est un pointeur, affectez\-lui la valeur `NULL`.  
  
5.  Remplacez le commentaire sur la logique de conversion par du code pour convertir le paramètre `from` en un objet de type *TO*.  Cet objet converti sera stocké dans `toPtr`.  
  
6.  Remplacez le commentaire sur la définition de `toObject` par du code pour affecter `toObject` à votre objet converti.  
  
7.  Remplacez le commentaire sur le nettoyage des ressources natives par du code pour libérer de la mémoire alloué par `toPtr`.  Si `toPtr` a alloué de la mémoire à l'aide de `new`, utilisez `delete` pour libérer celle\-ci.  
  
```  
namespace msclr {  
   namespace interop {  
      template<>  
      ref class context_node<TO, FROM> : public context_node_base  
      {  
      private:  
         TO toPtr;  
      public:  
         context_node(TO& toObject, FROM fromObject)  
         {  
            // (Step 4) Initialize toPtr to the appropriate empty value.  
            // (Step 5) Insert conversion logic here.  
            // (Step 6) Set toObject to the converted parameter.  
         }  
         ~context_node()  
         {  
            this->!context_node();  
         }  
      protected:  
         !context_node()  
         {  
            // (Step 7) Clean up native resources.  
         }  
      };  
   }  
}   
```  
  
## Exemple  
 L'exemple suivant étend la bibliothèque de marshaling avec une conversion ne requérant pas de contexte.  Dans cet exemple, le code convertit les informations sur l'employé à partir d'un type de données natif en un type de données managées.  
  
```  
// MyMarshalNoContext.cpp  
// compile with: /clr  
#include <msclr/marshal.h>  
  
value struct ManagedEmp {  
   System::String^ name;  
   System::String^ address;  
   int zipCode;  
};  
  
struct NativeEmp {  
   char* name;  
   char* address;  
   int zipCode;  
};  
  
namespace msclr {  
   namespace interop {  
      template<>  
      inline ManagedEmp^ marshal_as<ManagedEmp^, NativeEmp> (const NativeEmp& from) {  
         ManagedEmp^ toValue = gcnew ManagedEmp;  
         toValue->name = marshal_as<System::String^>(from.name);  
         toValue->address = marshal_as<System::String^>(from.address);  
         toValue->zipCode = from.zipCode;  
         return toValue;  
      }  
   }  
}  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {   
   NativeEmp employee;  
  
   employee.name = "Jeff Smith";  
   employee.address = "123 Main Street";  
   employee.zipCode = 98111;  
  
   ManagedEmp^ result = marshal_as<ManagedEmp^>(employee);  
  
   Console::WriteLine("Managed name: {0}", result->name);  
   Console::WriteLine("Managed address: {0}", result->address);  
   Console::WriteLine("Managed zip code: {0}", result->zipCode);  
  
   return 0;  
}  
```  
  
 Dans l'exemple précédent, la fonction `marshal_as` retourne un handle aux données converties.  Cela a été fait afin d'empêcher la création d'une copie supplémentaire des données.  Retourner la variable directement aurait un coût en termes de performances inutile qui lui serait associé.  
  
  **Managed name: Jeff Smith**  
**Managed address: 123 Main Street**  
**Managed zip code: 98111**   
## Exemple  
 L'exemple suivant convertit les informations sur l'employé à partir d'un type de données managées en un type de données natif.  Cette conversion requiert un contexte de marshaling.  
  
```  
// MyMarshalContext.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr/marshal.h>  
  
value struct ManagedEmp {  
   System::String^ name;  
   System::String^ address;  
   int zipCode;  
};  
  
struct NativeEmp {  
   const char* name;  
   const char* address;  
   int zipCode;  
};  
  
namespace msclr {  
   namespace interop {  
      template<>  
      ref class context_node<NativeEmp*, ManagedEmp^> : public context_node_base  
      {  
      private:  
         NativeEmp* toPtr;  
         marshal_context context;  
      public:  
         context_node(NativeEmp*& toObject, ManagedEmp^ fromObject)  
         {  
            // Conversion logic starts here  
            toPtr = NULL;  
  
            const char* nativeName;  
            const char* nativeAddress;  
  
            // Convert the name from String^ to const char*.  
            System::String^ tempValue = fromObject->name;  
            nativeName = context.marshal_as<const char*>(tempValue);  
  
            // Convert the address from String^ to const char*.  
            tempValue = fromObject->address;  
            nativeAddress = context.marshal_as<const char*>(tempValue);  
  
            toPtr = new NativeEmp();  
            toPtr->name = nativeName;  
            toPtr->address = nativeAddress;  
            toPtr->zipCode = fromObject->zipCode;  
  
            toObject = toPtr;  
         }  
         ~context_node()  
         {  
            this->!context_node();  
         }  
      protected:  
         !context_node()  
         {  
            // When the context is deleted, it will free the memory  
            // allocated for toPtr->name and toPtr->address, so toPtr  
            // is the only memory that needs to be freed.  
            if (toPtr != NULL) {  
               delete toPtr;  
               toPtr = NULL;  
            }  
         }  
      };  
   }  
}   
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   ManagedEmp^ employee = gcnew ManagedEmp();  
  
   employee->name = gcnew String("Jeff Smith");  
   employee->address = gcnew String("123 Main Street");  
   employee->zipCode = 98111;  
  
   marshal_context context;  
   NativeEmp* result = context.marshal_as<NativeEmp*>(employee);  
  
   if (result != NULL) {  
      printf_s("Native name: %s\nNative address: %s\nNative zip code: %d\n",  
         result->name, result->address, result->zipCode);  
   }  
  
   return 0;  
}  
```  
  
  **Native name: Jeff Smith**  
**Native address: 123 Main Street**  
**Native zip code: 98111**   
## Voir aussi  
 [Vue d'ensemble du marshaling dans C\+\+](../dotnet/overview-of-marshaling-in-cpp.md)