#User will input name

Name = input("What's the customer's name?:")

#User will choose drink and then input

Drink = input("Would you like Coffee or Tea?:")

if Drink.lower() == 'tea' or Drink.lower() == 't':
    Drink = "tea"
elif Drink.lower() == 'coffee' or Drink.lower() == 'c':
    Drink = 'coffee'
else:
    print('invalid input')
    exit ()

#User will decide which drink size they would like and then input

Size = input("Would you like a Small, Medium, or Large?:")

SmallPrice = float(1.50)
MediumPrice = float(2.50)
LargePrice = float(3.25)

if Size.lower() == 'small' or Size.lower() == 's':
    Size = 'small'
elif Size.lower() == 'medium'or Size.lower() == 'm':
    Size = 'medium'
elif Size.lower() == 'large' or Size.lower() == 'l':
    Size = 'large'
else:
    print('invalid input')
    exit()

#User will choose which flavor drink they would like and then input
#.lower() allows user to input any combination of lower case and upper case letters and allow the input to process correctly
#if statement allows user to choose which flavor an drink inout smoothly

Flavor = input("What flavor would you like? We have chocolate, vanilla, maple, or none for coffee, and lemon, mint, or none for tea.:")
if Drink == 'coffee' or Drink == 'Coffee' or Drink.lower() == 'c':
    if Flavor.lower() == 'vanilla' or Flavor.lower() == 'v':
        VanillaPrice = 0.25
        Flavor = 'Vanilla'
    elif Flavor.lower() == 'chocolate' or Flavor.lower() == 'c':
        ChocolatePrice = 0.75
        Flavor = 'Chocolate'
    elif Flavor.lower() == 'maple' or Flavor.lower() == 'm':
        MaplePrice = 0.50
        Flavor = 'Maple'
    elif Flavor.lower() == 'none' or Flavor.lower() == 'n':
        NonePrice = 0.0
        Flavor = 'None'
    else:
        print('invalid input')
        exit()
        
if Drink == 'tea' or Drink == 'Tea' or Drink.lower() == 't':
    if Flavor.lower() == 'lemon' or Flavor.lower() == 'l':
        LemonPrice = 0.25
        Flavor = 'Lemon'
    elif Flavor.lower() == 'mint' or Flavor.lower() == 'm':
        MintPrice = 0.50
        Flavor = 'Mint'
    elif Flavor.lower() == 'none' or Flavor.lower() == 'n':
        NonePrice = 0.00
        Flavor = 'None'
    else:
        print('Later sk8r boi')
        exit()
#tax will remain constant at 11% and be used later on
tax = 1.11
TotalCost = 0

#time to calculate the Total Cost of all the different order variations for coffee

if Drink == 'coffee' or Drink == 'Coffee' or Drink.lower() == 'c':
    if Flavor.lower() == 'chocolate' or Flavor.lower() == 'c':
        if(Size.lower() =='s' or Size == 'small' or Size == 'Small'):
            TotalCost = (ChocolatePrice + SmallPrice)*tax
        elif(Size.lower() == 'm' or Size == 'medium' or Size == 'Medium'):
            TotalCost = (ChocolatePrice + MediumPrice)*tax
        elif(Size.lower() == 'l' or Size == 'large' or Size == 'Large'):
            TotalCost = (ChocolatePrice + LargePrice)*tax
    if Flavor.lower() == 'vanilla' or Flavor.lower() == 'v':
        if(Size.lower() == 's' or Size == 'small' or Size == 'Small'):
            TotalCost = (VanillaPrice + SmallPrice)*tax
        elif(Size.lower() == 'm' or Size == 'medium' or Size == 'Medium'):
            TotalCost = (VanillaPrice + MediumPrice)*tax
        elif(Size.lower() == 'l' or Size == 'large' or Size == 'Large'):
            TotalCost = (VanillaPrice + LargePrice)*tax
    if Flavor.lower() == 'maple' or Flavor.lower() == 'm':
        if(Size.lower() == 's' or Size == 'small' or Size == 'Small'):
            TotalCost = (MaplePrice + SmallPrice)*tax
        elif(Size.lower() == 'm' or Size == 'medium' or Size == 'Medium'):
            TotalCost = (MaplePrice + MediumPrice)*tax
        elif(Size.lower() == 'l' or Size == 'large' or Size == 'Large'):
            TotalCost = (MaplePrice + LargePrice)*tax
    if Flavor.lower() == 'none' or Flavor.lower() == 'n':
        if(Size.lower() == 's' or Size == 'small' or Size == 'Small'):
            TotalCost = (NonePrice + SmallPrice)*tax
        elif(Size.lower() == 'm' or Size == 'medium' or Size == 'Medium'):
            TotalCost = (NonePrice + MediumPrice)*tax
        elif(Size.lower() == 'l' or Size == 'large' or Size == 'Large'):
            TotalCost = (NonePrice + LargePrice)*tax
            
#Time to calculate the total cost and all the different variations available for tea

if Drink == 'tea' or Drink == 'Tea' or Drink.lower() == 't':
    if Flavor.lower() == 'mint' or Flavor.lower() == 'm':
        if(Size.lower() == 's' or Size == 'small' or Size == 'Small'):
            TotalCost = (MintPrice + SmallPrice)*tax
        elif(Size.lower() == 'm' or Size == 'medium' or Size == 'Medium'):
            TotalCost = (MintPrice + MediumPrice)*tax
        elif(Size.lower() == 'l' or Size == 'large' or Size == 'Large'):
            TotalCost = (MintPrice + LargePrice)*tax
    if Flavor.lower() == 'lemon' or Flavor.lower() == 'l':
        if(Size.lower() == 's' or Size == 'small' or Size == 'Small'):
            TotalCost = (LemonPrice + SmallPrice)*tax
        elif(Size.lower() == 'm' or Size == 'medium' or Size == 'Medium'):
            TotalCost = (LemonPrice + MediumPrice)*tax
        elif(Size.lower() == 'l' or Size == 'large' or Size == 'Large'):
            TotalCost = (LemonPrice + LargePrice)*tax
    if Flavor.lower() == 'none' or Flavor.lower() == 'n':
        if(Size.lower() == 's' or Size == 'Small' or Size == 'small'):
            TotalCost = (NonePrice + SmallPrice)*tax
        elif(Size.lower() == 'm' or Size == 'medium' or Size == 'Medium'):
            TotalCost = (NonePrice + MediumPrice)*tax
        elif(Size.lower() == 'l' or Size == 'large' or Size == 'Large'):
            TotalCost = (NonePrice + LargePrice)*tax

#the final print statement should output the order
print('Order for',Name,'a',Size,Flavor,Drink,'Your cost will be:$','$%.2f'% TotalCost)

#'$%.2f' changes the excessive decimal places used to two decimal places
