---
layout: post
title: "Coffee speedruns!"
date: 2020-09-07 17:32:45 -0400
categories: elixir phoenix
---

<small>Building a simple CRUD app with elixir/phoenix</small>

# What's a coffee speedrun?

During the pre-pandemic times, (i.e. when we were still working in offices),
one of my favorite things to do when taking a break was to stroll down to
the local coffee shop in my office building and grab a coffee. I can't
exactly recall how it came about, but I got to thinking how fast I could
leave my desk, get a coffee, and get back to my desk. And thus, coffee
speedrunning was born.

# The tech

I decided to go with Elixir/Phoenix for this since I was (and still am)
interested in the [Elixir](https://elixir-lang.org/) programming language.

<section style="background-color:#F0F8FF; padding:3px; margin:20px; border-radius: 5px">
  <p>
    <b>Heavy disclaimer</b>: I am very much a novice when it comes to elixir/phoenix,
    and if I were doing this now I would have done some things differently.
  </p>
</section>

Phoenix makes setting up a CRUD backend extremely pain-free. Just run the
command

{% highlight bash %}

mix phx.new coffee_speedrun

{% endhighlight %}

and you're on your way!

In addition to the setup of the CRUD backend, Phoenix in conjuction with Ecto allows you to
quickly generate the database schema you'd like for your web application.

For my usecase, all we needed to store is the runner's name, and their time. This is easy enough
with

{% highlight bash %}

mix phx.gen.schema Runner runners name:string time:string

{% endhighlight %}

<section style="background-color:#F0F8FF; padding:3px; margin:20px; border-radius: 5px">
  <p>
      Perhaps I should have used an integer or time type for the runner's time, but this was the 
      simplest way with how I was creating the timing function.
  </p>
</section>

Now, we just need to connect all the dots.

# Connecting the dots

All I needed to do now was to add some Javascript to the index.html.eex file for the actual timer functionality, and to update the view upon each tick.

{% highlight javascript %}

async function increment_timer(time) {
    format_timer(time);
    await sleep(1000);
    time.seconds++;
    increment_timer(time);
}

{% endhighlight %}

<section style="background-color:#F0F8FF; padding:3px; margin:20px; border-radius: 5px">
  <p>
    <b>Note</b>: This is one of the areas that I would have done differently now. Rather than
    running this javascript in the index embedded-elixir file, I could have written this in elixir
    as well, passing the time over as a field on the Plug connection, or using LiveView (I haven't
    explored this yet, but would love to in the future).
  </p>
</section>

Now we just need to wire up the 'Start' and 'Stop' buttons to the proper actions ('Start' will
begin the timer, 'Stop' will POST the runner info and time to the server). Again, Phoenix has made
this very easy for us, as we already have the backend complete with interaction to our postgresql
database.

For displaying the leaderboard, all we need is a table with all of the result in our database. We
can do this with embedded-elixir. Something like

{% highlight elixir %}

<table style="width:100%">

  <tr>
    <th>Rank</th>
    <th>Runner Name</th>
    <th>Time</th>
  </tr>
  <%= for {runner, index} <- Enum.with_index(Enum.sort_by(@runners, fn t -> t.time end)) do %>

    <tr>
      <td>
        <%= index + 1 %>
      </td>

      <td>
        <%= runner.name %>
      </td>

      <td>
        <%=
         Time.to_string(runner.time)
         |> String.slice(3..-1)
        %>
      </td>
    </tr>

  <% end %>

</table>

{% endhighlight %}

does the trick.

And voila! We now have a simple CRUD app to track coffee speedruns, written in Elixir/Phoenix.

Check it out [here](https://www.speedrun.coffee)!


# Infrastructure

For hosting the web app, I decided to go with [heroku](https://www.heroku.com). The reason I went
this route was because of how easy they make the configuration. I also have some experience with
heroku in the past (my DnD website's backend is hosted on heroku). In addition, Hexdocs has a [very nice tutorial](https://hexdocs.pm/phoenix/heroku.html) for deploying phoenix apps to heroku.

As for the domain name, I decided to go with "speedrun.coffee". It was between this and
"coffeespeedrun.com", but the '.coffee' subdomain was too unique/funny to pass up. I purchased this
domain through [Namecheap](https://www.namecheap.com/).
