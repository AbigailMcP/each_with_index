#Some title here - using .each_with_index and .with_index methods

###Enumerables

- In order for a class to be able to use Enumerable, it must have an `each` method which yields each item in the collection to a block.

- Enumerable provides several functions for filtering collections

`2.3.0 :002 > Enumerable.instance_methods.sort
 => [:all?, :any?, :chunk, :chunk_while, :collect, :collect_concat, :count, :cycle, :detect, :drop, :drop_while, :each_cons, :each_entry, :each_slice, :each_with_index, :each_with_object, :entries, :find, :find_all, :find_index, :first, :flat_map, :grep, :grep_v, :group_by, :include?, :inject, :lazy, :map, :max, :max_by, :member?, :min, :min_by, :minmax, :minmax_by, :none?, :one?, :partition, :reduce, :reject, :reverse_each, :select, :slice_after, :slice_before, :slice_when, :sort, :sort_by, :take, :take_while, :to_a, :to_h, :zip]`
