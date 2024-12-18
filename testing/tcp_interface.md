Cluster -> Panels -> [TV or Presets -> Screens]

Area: A grouping a LED screens or TVs
Screens: logical preset
Layouts: Automatic or implicit


-- DB = {

    --   [cluster_id] = {

* id,
* offset, -- how far into list of sources are we offset
* manual_offset_adjustment -- overlap source pools
* width,
* height,
* layer_offset,
* videowall_offset,

    --     [preset_id] = {

    --       offset_x, offset_y, collumns, preset_name, preset_inheritance

    --       [region_id] = {

    --         x, y, w, h, source, default, (override) -- override is should not be saved to the DB

    -- } } } }

DB [areas] {

    [area_id] {1,2,3,4}, ...

}
DB [names] {} -- screen names
