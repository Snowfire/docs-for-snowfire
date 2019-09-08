# Search

This is an example for building site search on Snowfire

## search.tpl

```html
[% set result = searchResult('q: ' ~ request('get: q')) %]
[% set current = current() %]

<div class="sf-search-box">
    <form method="get" action="[[ current.page.url ]]">
        <input type="search" name="q" value="[[ request('get: q') ]]">
        <button type="submit">Search</button>
    </form>
</div>

[% if (result.status == 'error') %]
    <div class="sf-search-results-error">
        There was a problem with this search, please try again later
    </div>
[% endif %]

[% if (result.hits > 0) %]
    <div class="sf-search-results">
        [% for page in result.pages %]
            <div class="sf-search-result">
                <div class="sf-search-result-title">
                    <a href="/[[ page.link ]]">[[ page.title | raw ]]</a>
                </div>
                <div class="sf-search-result-link">
                    <a href="/[[ page.link ]]">[[ page.url ]]</a>
                </div>
                <div class="sf-search-result-description">
                    [[ page.description | raw ]]
                </div>
            </div>
        [% endfor %]
    </div>
[% endif %]

[% if (result.pagination.pages > 1) %]
    <div class="sf-search-pagination">
        [% if (result.pagination.previous_url) %]
            <div class="sf-search-pagination-previous">
                <a href="[[ result.pagination.previous_url ]]">
                    <svg width="6" height="8" viewBox="0 0 6 8" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M0.784378 4.26563L4.46562 7.89063C4.6125 8.0375 4.85 8.0375 4.99687 7.89063L5.21875 7.66875C5.36562 7.52188 5.36562 7.28438 5.21875 7.1375L2.02188 4L5.21562 0.862503C5.3625 0.715628 5.3625 0.478128 5.21562 0.331253L4.99375 0.109378C4.84687 -0.0374969 4.60937 -0.0374969 4.4625 0.109378L0.781253 3.73438C0.637503 3.88125 0.637503 4.11875 0.784378 4.26563V4.26563Z" fill="#3B3D44"/></svg>
                </a>
            </div>
        [% endif %]
        
        <div class="sf-search-pagination-current">
            [[ result.pagination.page ]] / [[ result.pagination.pages ]]
        </div>
        
        [% if (result.pagination.next_url) %]
            <div class="sf-search-pagination-next">
                <a href="[[ result.pagination.next_url ]]">
                    <svg width="5" height="9" viewBox="0 0 5 9" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M4.88945 4.73359L1.2082 1.10859C1.06133 0.961719 0.82383 0.961719 0.676955 1.10859L0.45508 1.33047C0.308206 1.47734 0.308206 1.71484 0.45508 1.86172L3.65195 4.99922L0.458206 8.13672C0.311331 8.28359 0.311331 8.52109 0.458206 8.66797L0.680081 8.88984C0.826955 9.03672 1.06445 9.03672 1.21133 8.88984L4.89258 5.26484C5.03633 5.11797 5.03632 4.88047 4.88945 4.73359V4.73359Z" fill="#3B3D44"/></svg>
                </a>
            </div>
        [% endif %]
    </div>
[% endif %]
```
