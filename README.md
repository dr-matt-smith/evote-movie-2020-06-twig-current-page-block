# evote-movie-2020-06-twig-current-page-block

- add a uniquely named Twig block for the CSS link style for each link in the nav bar, in the form `{% block homeLinkStyle %}{% endblock %}`:
    
    ```twig
    <li>
        <a href="/" class="{% block homeLinkStyle %}{% endblock %}">Home</a>
    </li>
    
    <li>
    <a href="/index.php?action=about" class="{% block aboutLinkStyle %}{% endblock %}">About Us</a>
    </li>
    
    <li>
        <a href="/index.php?action=list" class="{% block listLinkStyle %}{% endblock %}">Movie ratings</a>
    </li>
    
    <li>
        <a href="/index.php?action=contact" class="{% block contactLinkStyle %}{% endblock %}">Contact Us</a>
    </li>
    
    <li>
        <a href="/index.php?action=sitemap" class="{% block mapLinkStyle %}{% endblock %}">Site Map</a>
    </li>
    ```
  
- edit each page template to set its link style block to contain `current_page`, e.g. for the home page template `/templates/index.html.twig` we declare content `current_page` for the `homeLinkStyle` block:

    ```twig
    {% extends '_base.html.twig' %}
    
    {% block homeLinkStyle %}current_page{% endblock %}
    
    {% block title %}home page{% endblock %}
    
    {% block main %}
        <h1>
        Welcome to SmithIT Home Page
        </h1>
    
        <p>
        This site offers you the chance to VOTE on your favourite movies ...
        </p>
    {% endblock %}
    ```

- The means each navbar link has a `<style=""` attribute, but only the link for the current page as a value for this attribute, e.g. for the home page the navbar is as follows:

    ```html
    <li>
        <a href="/" class="current_page">Home</a>
    </li>
    
    <li>
    <a href="/index.php?action=about" class="">About Us</a>
    </li>
    
    and so on ...
    ```