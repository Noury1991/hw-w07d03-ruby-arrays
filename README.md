# Ruby Map Practice

![ARRAYS](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQVWBMdo6Ac3moY3tPnzMsFVnOscOR03SxkZ4sPGGhsWoQrYMPZ9g)

## 1. Return an array of each Student's full name, upper-cased

```rb

students = [
  {
      first_name: 'Lamees',
      last_name: 'AlFallaj'
  },
  {
      first_name: 'Aisha',
      last_name: 'AlDabbagh',
  },
  {
      first_name: 'Abdulwahhab',
      last_name: 'AlBalla',
  }
]

upper_case_full_names = []

```

### Answer

 students.map do |student|
    upper_case_full_names.push(("#{student[:first_name]} #{student[:last_name]}").upcase)
 end
 p upper_case_full_names

```rb
LAMEES ALFALLAJ
AISHA ALDABBAGH
ABDULWAHHAB ALBALLA
```

## 2. Find the first order for each user

```rb

users = [
  {
      name: 'Fahad',
      orders: [
          {
              description: 'a bike'
          }
      ]
  },
  {
      name: 'Abdulrahman',
      orders: [
          {
              description: 'bees'
          },
          {
              description: 'fishing rod'
          }
      ]
  },
  {
      name: 'Muhannad',
      orders: [
          {
              description: 'a MacBook'
          },
          {
              description: 'The West Wing DVDs'
          },
          {
              description: 'headphones'
          },
          {
              description: 'a kitten'
          }
      ]
  }
]

first_order_for_each_user = []

```

### Answer

  users.each do |user| 
    first_order_for_each_user.push(user[:orders].first)
  end

p first_order_for_each_user

```rb

{:description=>"a bike"}
{:description=>"bees"}
{:description=>"a MacBook"}

```

## 3. Find the average amount spent on coffee, per transaction, for each person

```rb

people = [
  {
      name: 'Sarah',
      transactions: [
          {
              type: 'COFFEE',
              amount: 7.43
          },
          {
              type: 'TACOS',
              amount: 14.65
          },
          {
              type: 'COFFEE',
              amount: 4.43
          }
      ]
  },
  {
      name: 'Saud',
      transactions: [
          {
              type: 'BIKES',
              amount: 800.00
          },
          {
              type: 'TACOS',
              amount: 14.65
          },
          {
              type: 'COFFEE',
              amount: 4.43
          }
      ]
  },
  {
      name: 'Norah',
      transactions: [
          {
              type: 'COFFEE',
              amount: 7.43
          },
          {
              type: 'COFFEE',
              amount: 100.00
          },
          {
              type: 'COFFEE',
              amount: 4.43
          }
      ]
  }
]


coffee_average_per_person = []

```

### Answer
  people.each{|person| 
    coffee = 0
    sum = 0
    person[:transactions].each do |transaction|
         if (transaction[:type] == "COFFEE")
            coffee += 1
            sum += transaction[:amount]
        end

    end
    coffee_average_per_person.push("#{person[:name]}, #{sum / coffee}")
}
p coffee_average_per_person

```rb

{:name=>"Sarah", :coffee_average=>5.93}
{:name=>"Saud", :coffee_average=>4.43}
{:name=>"Norah", :coffee_average=>37.28666666666667}

```

## 4. Find the most expensive product for each store, with the store name:

```rb

stores = [
  {
      store_name: 'Jarir',
      products: [
          {
              description: 'Titanium',
              price: 9384.33
          },
          {
              description: 'Gold',
              price: 345.54
          }
      ]
  },
  {
      store_name: 'Tamimi',
      products: [
          {
              description: 'Silver',
              price: 654.44
          },
          {
              description: 'Ruby',
              price: 323.43
          }
      ]
  },
  {
      store_name: 'Souq',
      products: [
          {
              description: 'Opal',
              price: 345.43
          },
          {
              description: 'Sapphire',
              price: 899.33
          }
      ]
  }
]

most_expensive_products_by_store = []

```

### Answer
most_expensive_products_by_store = stores.map do |store|
    most_price=0
    item =''
        store[:products].each do |product|
            if product[:price]> most_price
                item = product[:description] 
                most_price= product[:price]
            end
        end
        {store_name:store[:store_name], most_expensive_product: item, price:most_price}
      end

      p most_expensive_products_by_store


```rb

{:store_name=>"Jarir", :most_expensive_product=>{:description=>"Titanium", :price=>9384.33}}
{:store_name=>"Tamimi", :most_expensive_product=>{:description=>"Silver", :price=>654.44}}
{:store_name=>"Souq", :most_expensive_product=>{:description=>"Sapphire", :price=>899.33}}

```

# Bonus

Write an infinite loop that will make you add all the your friends in the students list and after each add will ask if you want to quit the loop (yes/no) if the user choose no print all the students array

### Answer

```

add a student
Mohammed AlOfaysan
Do you want to continue ? (y/n)
y
add a student
Raje AlHarthi
Do you want to continue ? (y/n)
y
add a student

```
