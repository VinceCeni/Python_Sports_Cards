Hello and welcome to my Sports Cards database application README.md! You'll find you can add, delete and make queries with several different pieces of information. It's rewarding to see all of these different programs come together and I'll be developing an app of my own at some point in the future! Enclosed in this README.md you'll find screenshots and snippets of my code and also functions I've created. If you have any questions, please feel free to contact me!

def join(request):
    form = CardForm(request.POST or None)
    if request.method == "POST":
        if form.is_valid():
            form.save()
            return redirect("SportsCards_join")

    return render(request, 'sportscards/join.html', {"form":form})

def display(request):
    all_cards = Card.objects.all()
    return render(request, 'sportscards/sportscards_display.html', {'all_cards':all_cards})
    
These functions define the Form a user would use to add an item into the database and then how that item's information would be displayed back to the user.
