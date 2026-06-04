# Bubble Sort

![Ruby](https://img.shields.io/badge/Ruby-CC342D?style=flat&logo=ruby&logoColor=white)
![The Odin Project](https://img.shields.io/badge/The%20Odin%20Project-Curriculum-brightgreen)

## Description

A Ruby implementation of the Bubble Sort algorithm built as part of [The Odin Project](https://www.theodinproject.com/) curriculum. Bubble sort is one of the simplest sorting algorithms — it repeatedly compares adjacent elements and swaps them if they are in the wrong order, continuing until the array is fully sorted.

---

## Table of Contents

- [Usage](#usage)
- [Examples](#examples)
- [How It Works](#how-it-works)
- [Installation](#installation)
- [What I Learned](#what-i-learned)

---

## Usage

```ruby
bubble_sort([4, 3, 78, 2, 0, 2])
```

---

## Examples

```ruby
> bubble_sort([4, 3, 78, 2, 0, 2])
=> [0, 2, 2, 3, 4, 78]
```

---

## How It Works

1. Start with an `unsorted` flag set to `true` to enter the loop
2. At the beginning of each pass, assume the array is sorted (`unsorted = false`)
3. Iterate over every adjacent pair of elements
4. If the left element is greater than the right, swap them and mark `unsorted = true`
5. If a full pass completes with no swaps, the array is sorted and the loop stops

```ruby
def bubble_sort(array)
  n = array.length
  unsorted = true

  while unsorted == true do
    unsorted = false

    array.each_with_index do |num, i|
      if i == 0
        next
      elsif array[i - 1] > array[i]
        array[i - 1], array[i] = array[i], array[i - 1]
        unsorted = true
      end
    end

    n = n - 1
  end

  p array
end
```

---

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/bubble-sort.git
```

2. Navigate into the project:
```bash
cd bubble-sort
```

3. Run the file:
```bash
ruby bubble_sort.rb
```

> No gems or dependencies required — pure Ruby.

---

## What I Learned

- How bubble sort works as an algorithm — comparing adjacent pairs and swapping until sorted
- How to use a boolean flag (`unsorted`) to control a `while` loop
- Why the flag needs to reset at the start of each pass, not once before the loop
- How variable naming affects readability — `unsorted = true` reads more naturally than `swapped = false`
- How to skip the first index in `each_with_index` using `next` to avoid an out-of-bounds comparison with `array[-1]`
- How Ruby's parallel assignment makes swapping two values clean and concise: `a, b = b, a`

---

## Project

This project is part of the [Ruby Programming path](https://www.theodinproject.com/paths/full-stack-ruby-on-rails/courses/ruby) on The Odin Project.