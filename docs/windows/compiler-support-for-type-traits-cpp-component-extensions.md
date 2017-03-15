---
title: "Prise en charge du compilateur pour les Type Traits (extensions du composant C++) | Microsoft Docs"
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
  - "__is_simple_value_class"
  - "__has_trivial_destructor"
  - "__has_assign"
  - "__is_union"
  - "__is_class"
  - "__is_abstract"
  - "__has_trivial_assign"
  - "__has_virtual_destructor"
  - "__is_ref_array"
  - "__is_base_of"
  - "__has_copy"
  - "__is_polymorphic"
  - "__has_nothrow_constructor"
  - "__is_ref_class"
  - "__is_delegate"
  - "__is_convertible_to"
  - "__is_value_class"
  - "__is_interface_class"
  - "__has_nothrow_copy"
  - "__is_sealed"
  - "__has_trivial_constructor"
  - "__has_trivial_copy"
  - "__is_enum"
  - "__has_nothrow_assign"
  - "__has_finalizer"
  - "__is_empty"
  - "__is_pod"
  - "__has_user_destructor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__is_class (mot clé) (C++)"
  - "__is_pod (mot clé) (C++)"
  - "__is_delegate (mot clé) (C++)"
  - "__is_value_class (mot clé) (C++)"
  - "__has_copy (mot clé) (C++)"
  - "__has_nothrow_copy (mot clé) (C++)"
  - "__is_interface_class (mot clé) (C++)"
  - "__is_sealed (mot clé) (C++)"
  - "__is_convertible_to (mot clé) (C++)"
  - "__is_ref_class (mot clé) (C++)"
  - "__has_trivial_copy (mot clé) (C++)"
  - "__has_user_destructor (mot clé) (C++)"
  - "__is_abstract (mot clé) (C++)"
  - "__is_empty (mot clé) (C++)"
  - "__has_trivial_assign (mot clé) (C++)"
  - "__has_nothrow_constructor (mot clé) (C++)"
  - "__is_ref_array (mot clé) (C++)"
  - "__is_base_of (mot clé) (C++)"
  - "__has_nothrow_assign (mot clé) (C++)"
  - "__has_virtual_destructor (mot clé) (C++)"
  - "__has_finalizer (mot clé) (C++)"
  - "__is_union (mot clé) (C++)"
  - "__has_assign (mot clé) (C++)"
  - "__has_trivial_destructor (mot clé) (C++)"
  - "__is_polymorphic (mot clé) (C++)"
  - "__is_enum (mot clé) (C++)"
  - "__is_simple_value_class (mot clé) (C++)"
  - "__has_trivial_constructor (mot clé) (C++)"
ms.assetid: cd440630-0394-48c0-a16b-1580b6ef5844
caps.latest.revision: 27
caps.handback.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Prise en charge du compilateur pour les Type Traits (extensions du composant C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La prise en charge du compilateur *type traits*, qui indiquent les différentes caractéristiques d’un type au moment de la compilation.  
  
## <a name="all-runtimes"></a>Tous les runtimes  
 **Section Notes**  
  
 Les traits de type s'avèrent particulièrement utiles pour les programmeurs qui écrivent des bibliothèques.  
  
 La liste suivante contient les caractéristiques de type prises en charge par le compilateur. Tous les traits de type retournent `false` si la condition spécifiée par le nom du trait de type n'est pas remplie.  
  
 (Dans la liste suivante, les exemples de code sont écrits uniquement dans [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)]. Mais le trait de type correspondant est également pris en charge dans [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)] sauf indication contraire. Le terme « type de plateforme » fait référence aux types [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] ou aux types du Common Language Runtime.)  
  
-   `__has_assign(` `type` `)`  
  
     Retourne la valeur true si le type de plateforme ou natif possède un opérateur d'assignation de copie.  
  
    ```  
  
    ref struct R {  
    void operator=(R% r) {}  
    };  
  
    int main() {  
    System::Console::WriteLine(__has_assign(R));  
    }  
  
    ```  
  
-   `__has_copy(` `type` `)`  
  
     Retourne la valeur true si le type de plateforme ou natif possède un constructeur de copie.  
  
    ```  
  
    ref struct R {  
    R(R% r) {}  
    };  
  
    int main() {  
    System::Console::WriteLine(__has_copy(R));  
    }  
  
    ```  
  
-   `__has_finalizer(` `type` `)`  
  
     (Non pris en charge dans [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)].) Retourne la valeur true si le type CLR a un finaliseur. Consultez [destructeurs et finaliseurs dans Visual C++](../misc/destructors-and-finalizers-in-visual-cpp.md) Pour plus d’informations.  
  
    ```  
  
    using namespace System;  
    ref struct R {  
    ~R() {}  
    protected:  
    !R() {}  
    };  
  
    int main() {  
    Console::WriteLine(__has_finalizer(R));  
    }  
  
    ```  
  
-   `__has_nothrow_assign(` `type` `)`  
  
     Retourne la valeur true si un opérateur d'assignation de copie a une spécification d'exception vide.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    void operator=(S& r) throw() {}  
    };  
  
    int main() {  
    __has_nothrow_assign(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_nothrow_constructor(` `type` `)`  
  
     Retourne la valeur true si le constructeur par défaut a une spécification d'exception vide.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    S() throw() {}  
    };  
  
    int main() {  
    __has_nothrow_constructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_nothrow_copy(` `type` `)`  
  
     Retourne la valeur true si le constructeur de copie a une spécification d'exception vide.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    S(S& r) throw() {}  
    };  
  
    int main() {  
    __has_nothrow_copy(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_assign(` `type` `)`  
  
     Retourne la valeur true si le type a un opérateur d'assignation trivial généré par le compilateur.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_assign(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_constructor(` `type` `)`  
  
     Retourne la valeur true si le type a un constructeur trivial généré par le compilateur.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_constructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_copy(` `type` `)`  
  
     Retourne la valeur true si le type a un constructeur de copie trivial généré par le compilateur.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_copy(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_destructor(` `type` `)`  
  
     Retourne la valeur true si le type a un destructeur trivial généré par le compilateur.  
  
    ```  
  
    // has_trivial_destructor.cpp  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_destructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_user_destructor(` `type` `)`  
  
     Retourne la valeur true si le type de plateforme ou natif a un destructeur déclaré par l'utilisateur.  
  
    ```  
  
    // has_user_destructor.cpp  
  
    using namespace System;  
    ref class R {  
    ~R() {}  
    };  
  
    int main() {  
    Console::WriteLine(__has_user_destructor(R));  
    }  
  
    ```  
  
-   `__has_virtual_destructor(` `type` `)`  
  
     Retourne la valeur true si le type a un destructeur virtuel.  
  
     `__has_virtual_destructor` fonctionne également sur les types de plateforme et tout destructeur défini par l'utilisateur dans un type de plateforme est un destructeur virtuel.  
  
    ```  
  
    // has_virtual_destructor.cpp  
    #include <stdio.h>  
    struct S {  
    virtual ~S() {}  
    };  
  
    int main() {  
    __has_virtual_destructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_abstract(` `type` `)`  
  
     Retourne la valeur true si le type est un type abstrait. Pour plus d’informations sur les types abstraits natifs, consultez [abstraite](../windows/abstract-cpp-component-extensions.md).  
  
     `__is_abstract` fonctionne également pour les types de plateforme. Une interface avec au moins un membre est un type abstrait, à l'instar d'un type référence avec au moins un membre abstrait. Pour plus d’informations sur les types de plateforme abstrait, voir [des Classes abstraites](../cpp/abstract-classes-cpp.md)  
  
    ```  
  
    // is_abstract.cpp  
    #include <stdio.h>  
    struct S {  
    virtual void Test() = 0;  
    };  
  
    int main() {  
    __is_abstract(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_base_of(` `base` `,` `derived` `)`  
  
     Retourne la valeur true si le premier type est une classe de base du second type, ou si ces deux types sont les mêmes.  
  
     `__is_base_of` fonctionne également sur les types de plateforme. Par exemple, il renvoie la valeur true si le premier type est une [classe d’interface](../windows/interface-class-cpp-component-extensions.md) et le second type implémente l’interface.  
  
    ```  
  
    // is_base_of.cpp  
    #include <stdio.h>  
    struct S {};  
    struct T : public S {};  
  
    int main() {  
    __is_base_of(S, T) == true ?  
    printf("true\n") : printf("false\n");  
  
    __is_base_of(S, S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_class(` `type` `)`  
  
     Retourne la valeur true si le type est une classe native ou un struct natif.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __is_class(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_convertible_to(` `from` `,`  `to` `)`  
  
     Retourne la valeur true si le premier type peut être converti en second type.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
    struct T : public S {};  
  
    int main() {  
    S * s = new S;  
    T * t = new T;  
    s = t;  
    __is_convertible_to(T, S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_delegate(` `type` `)`  
  
     Retourne la valeur true si `type` est un délégué. Pour plus d’informations, consultez [délégué (Extensions du composant C++)](../windows/delegate-cpp-component-extensions.md).  
  
    ```  
  
    delegate void MyDel();  
    int main() {  
    System::Console::WriteLine(__is_delegate(MyDel));  
    }  
  
    ```  
  
-   `__is_empty(` `type` `)`  
  
     Retourne la valeur true si le type ne possède aucun membre de données d'instance.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    int Test() {}  
    static int i;  
    };  
    int main() {  
    __is_empty(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_enum(` `type` `)`  
  
     Retourne la valeur true si le type est un enum natif.  
  
    ```  
  
    // is_enum.cpp  
    #include <stdio.h>  
    enum E { a, b };  
  
    struct S {  
    enum E2 { c, d };  
    };  
  
    int main() {  
    __is_enum(E) == true ?  
    printf("true\n") : printf("false\n");  
  
    __is_enum(S::E2) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_interface_class(` `type` `)`  
  
     Retourne la valeur true si une interface de plateforme est passée. Pour plus d’informations, consultez [classe d’interface](../windows/interface-class-cpp-component-extensions.md).  
  
    ```  
  
    // is_interface_class.cpp  
  
    using namespace System;  
    interface class I {};  
    int main() {  
    Console::WriteLine(__is_interface_class(I));  
    }  
  
    ```  
  
-   `__is_pod(` `type` `)`  
  
     Retourne la valeur true si le type est une classe ou une union sans aucun constructeur ni aucun membre non static privé ou protégé, ni aucune classe de base ni aucune fonction virtuelle. Consultez la norme C++, sections 8.5.1/1, 9/4 et 3.9/10 pour plus d'informations sur les POD.  
  
     `__is_pod` retourne la valeur false sur les types fondamentaux.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __is_pod(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_polymorphic(` `type` `)`  
  
     Retourne la valeur true si un type natif possède des fonctions virtuelles.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    virtual void Test(){}  
    };  
  
    int main() {  
    __is_polymorphic(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_ref_array(` `type` `)`  
  
     Retourne la valeur true si un tableau de plateforme est passé. Pour plus d’informations, consultez [tableaux](../windows/arrays-cpp-component-extensions.md).  
  
    ```  
  
    using namespace System;  
    int main() {  
    array<int>^ x = gcnew array<int>(10);  
    Console::WriteLine(__is_ref_array(array<int>));  
    }  
  
    ```  
  
-   `__is_ref_class(` `type` `)`  
  
     Retourne la valeur true si une classe de référence est passée. Pour plus d’informations sur les types référence définis par l’utilisateur, consultez la page [les Classes et Structs](../windows/classes-and-structs-cpp-component-extensions.md).  
  
    ```  
  
    using namespace System;  
    ref class R {};  
    int main() {  
    Console::WriteLine(__is_ref_class(Buffer));  
    Console::WriteLine(__is_ref_class(R));  
    }  
  
    ```  
  
-   `__is_sealed(` `type` `)`  
  
     Retourne la valeur true si un type de plateforme ou natif marquée comme sealed est passé. Pour plus d’informations, consultez [scellé](../windows/sealed-cpp-component-extensions.md).  
  
    ```  
  
    ref class R sealed{};  
    int main() {  
    System::Console::WriteLine(__is_sealed(R));  
    }  
  
    ```  
  
-   `__is_simple_value_class(` `type` `)`  
  
     Retourne la valeur true si un type valeur qui ne contient aucune référence au tas récupéré par le garbage collector est passé. Pour plus d’informations sur les types valeur définis par l’utilisateur, consultez la page [les Classes et Structs](../windows/classes-and-structs-cpp-component-extensions.md).  
  
    ```  
  
    using namespace System;  
    ref class R {};  
    value struct V {};  
    value struct V2 {  
    R ^ r;   // not a simnple value type  
    };  
  
    int main() {  
    Console::WriteLine(__is_simple_value_class(V));  
    Console::WriteLine(__is_simple_value_class(V2));  
    }  
  
    ```  
  
-   `__is_union(` `type` `)`  
  
     Retourne la valeur true si un type est une union.  
  
    ```  
  
    #include <stdio.h>  
    union A {  
    int i;  
    float f;  
    };  
  
    int main() {  
    __is_union(A) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_value_class(` `type` `)`  
  
     Retourne la valeur true si un type valeur est passé. Pour plus d’informations sur les types valeur définis par l’utilisateur, consultez la page [les Classes et Structs](../windows/classes-and-structs-cpp-component-extensions.md).  
  
    ```  
  
    value struct V {};  
  
    int main() {  
    System::Console::WriteLine(__is_value_class(V));  
    }  
  
    ```  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Section Notes**  
  
 Le `__has_finalizer(`*type*`)` caractéristique de type n’est pas pris en charge, car cette plate-forme ne prend pas en charge les finaliseurs.  
  
### <a name="requirements"></a>Spécifications  
 Option du compilateur : **/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Section Notes**  
  
 (Il n’existe aucune note spécifique à la plateforme pour cette fonctionnalité.)  
  
### <a name="requirements"></a>Spécifications  
 Option du compilateur : **/clr**  
  
### <a name="examples"></a>Exemples  
 **Exemple**  
  
 L’exemple de code suivant montre comment utiliser un modèle de classe pour exposer un trait de type du compilateur pour un **/clr** compilation. Pour plus d’informations, consultez [Windows Runtime et modèles gérés](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md).  
  
```  
// compiler_type_traits.cpp  
// compile with: /clr  
using namespace System;  
  
template <class T>  
ref struct is_class {  
   literal bool value = __is_ref_class(T);  
};  
  
ref class R {};  
  
int main () {  
   if (is_class<R>::value)  
      Console::WriteLine("R is a ref class");  
   else  
      Console::WriteLine("R is not a ref class");  
}  
```  
  
 **Sortie**  
  
```Output  
R is a ref class  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Extensions du composant pour les plateformes Runtime](../windows/component-extensions-for-runtime-platforms.md)