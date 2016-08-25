#Using each_with_index and with_index

###Enumerables

- Enumerable is a Ruby module, a collection of methods that can get 'mixed in' with other classes

- In order for a class to be able to use Enumerable, it must have an `each` method which yields each item in the collection to a block

- Enumerable is great in providing lots of useful ways of iterating through and filtering your collections:

`> Enumerable.instance_methods.sort
 => [:all?, :any?, :chunk, :chunk_while, :collect, :collect_concat, :count, :cycle, :detect, :drop, :drop_while, :each_cons, :each_entry, :each_slice, :each_with_index, :each_with_object, :entries, :find, :find_all, :find_index, :first, :flat_map, :grep, :grep_v, :group_by, :include?, :inject, :lazy, :map, :max, :max_by, :member?, :min, :min_by, :minmax, :minmax_by, :none?, :one?, :partition, :reduce, :reject, :reverse_each, :select, :slice_after, :slice_before, :slice_when, :sort, :sort_by, :take, :take_while, :to_a, :to_h, :zip]`


###Using the each method

... for completeness only!

- `each` on its own is a handy method known as an iterator

- it cycles through each element in your collection and runs the block of code passed to it

Given an array:

`pets = [:cat, :dog, :antelope, :bacterium]`

we can cycle through the elements using `each`:

`pets.each {|pet| puts "I love my #{pet}"}`

and return:

```
I love my cat
I love my dog
I love my antelope
I love my bacterium
```

*Woah, slow down there!*


###Show me the numbers!

- `each_with_index` extends the `each` method in providing both a reference to each element in the Array and that element's numerical position (ie its index) in the array

- takes an extra argument (the index) which can then be used inside the block of code passed to it

```
pets.each_with_index {|pet,index| puts "My #{pet} is stored in cage number #{index}"}

=> My cat is stored in cage number 0
My dog is stored in cage number 1
My antelope is stored in cage number 2
My bacterium is stored in cage number 3
```

- can be used for returning all numbered objects:

```
pets.each_with_index {|pet, index| puts pet if index%2 == 0}

=> [:cat, :antelope]
```


###Comparison with `each.with_index`

- `each_with_index` came first, `with_index` then followed

- `with_index` is a chainable method which was introduced to allow wider usage with different enumerators

- `with_index` also allows you to pass an optional parameter to offset the starting index:

```
pets.each.with_index(1) {|pet, index| puts "#{pet} is my number #{index} homie"}

=> cat is my number 1 homie
dog is my number 2 homie
antelope is my number 3 homie
bacterium is my number 4 homie
```

- This is useful for counting like a bona fide human rather than a programmer

(Note that this doesn't change the index of each element, it merely adds 1 to the index)


###Using with_index

```
pets.map.with_index(1).to_a

=> [[:cat, 1], [:dog, 2], [:antelope, 3], [:bacterium, 4]]
```
