# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    The router defines each route handler for the URL making it possible to
    render different view states in the application.

    Templates in the application are backed by the model. You can tell a template
    which model it should render by defining a route with the same name as the template,
    and implementing its model hook.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    In the campus handlebars template you can add in the appropriate link that will
    take you to the nested URL, in this case campus/boston.

    {{#link-to 'campus.boston'}}Boston{{/link-to}}

    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    The first route definition has a nested URL. It is creating two separate URLs,
    so in the first example you have a route that directs you to all the products
    and within that route that you have a dynamic route defined for a single product.
    This allows for the product template to render inside of the products template.

    The second definition only defines the route for a product, however, its path
    includes products. We simply won't be be able to render the template within
    products.  
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    Params allows us to extract the value of the id from the URL as so:

    params.movie_id
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    We can reference the data simply by calling the model that the route contains
    and using dot notation to pull specific information.
    Example: {{model.name}}
    ```
