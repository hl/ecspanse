# Getting Started

There are a few steps needed to get started with the Ecspanse ECS framework. This guide covers the process of setting up the environment and creating a working application.

## Create a new Elixir/Phoenix project

This guide we will use a simple supervised Elixir application:

```bash
mix new demo --sup
```

## Installation

The first step is adding the `:ecspanse` library to the project dependencies. This is done by adding the following line to the `mix.exs` file:

```elixir
def deps do
  [
    {:ecspanse, "~> 0.8.0"}
  ]
end
```

## Setup

The subsequent stage involves configuring Ecspanse via `use Ecspanse`. In this guide, the primary Demo module will accommodate the Ecspanse setup:

```elixir
defmodule Demo do
  use Ecspanse

  @impl Ecspanse
  def setup(data) do
    data
  end
end
```

The `c:Ecspanse.setup/1` callback is mandatory. It will be used later on to schedule the application systems.

## Starting the Ecspanse server

The module implementing `Ecspanse` needs to be added to the supervision tree.

The Ecspanse server loop will start together with the application:

```bash
iex -S mix
```
