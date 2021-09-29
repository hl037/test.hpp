Some utility code coming with catch2 to simplify writing parametric tests.

Installation : 

(on archlinux)

```
makepkg
pacman -U *.pkg
```

Usage :

```
#include <hl037/test>

DECLARE_PARAMS_SECTION(Section_name_as_valid_identifier){

DECLARE_PARAM_TYPE{ // Declare a struct that will be used as parameterized parameter type.
  const char * name; // mendatory, name of the specific test case
  const std::initializer_list<std::pair<int, int> > param1;
  //... Any struct field you want to be in the parameterized parameters
};

DECLARE_DATA_CASE(simple) { // Declare a set of test case data
  { // First data case
    "Empty", // name
    {}, // param1
    // ... Other params
    // if your compiler support C99 (extension), you can also use .param = ...
  },
  // ... Other data cases
};

DECLARE_DATA_CASE(other_data) {
  // ...
};



// You may declare some template here
DATA_CASE_TEST(/*First param mendatory*/ PARAM_TYPE param, /* Some other Data case constant you may want to pass*/){
  for(auto && p:param.param1){ // Do whatever you want with the fields of param (the same you declared earlier
    REQUIRE(p.first < p.second // Do assertions
  }
}

};


// Later...

//Declare your test as usual
TEST_CASE("rangeset merge touching"){
  
  BEGIN_PARAMS_SECTION(Section_name_as_valid_identifier)
    // Tests insert(pair), insert(start, end), const_iterator, cbegin, cend, size, 
    DATA_CASE(simple, /* Correspounding data case constants */)
    DATA_CASE(other_data, /* ...*/)
  END
}

// That's all. 
```

To see a reference uasage, go to https://github.com/hl037/rangeset.hpp


