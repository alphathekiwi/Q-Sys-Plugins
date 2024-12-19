Cluster -> Panels -> [TV or Presets -> Screens]

Area: A grouping a LED screens or TVs
Screens: logical preset
Layouts: Automatic or implicit


-- DB = {
[cluster_id] = {
* width,
* height,

* id,
* manual_offset_adjustment -- overlap source pools
* offset, -- how far into list of sources are we offset
* layer_offset,
* videowall_offset,
    --     [preset_id] = {
            --       offset_x, offset_y, collumns, preset_name, preset_inheritance
        --       [region_id] = {
            --         x, y, w, h, source, default, (override) -- override is should not be saved to the DB
} } } }


DB [areas] { -- area and up to four clusters as children
    [AREA_ID] {1,2,3,4}, ...
}
DB [names] {'name', ...} -- screen names
DB [layouts] {
	[LAYOUT_ID] = {
        columns -- for display width 30 or 28
        maximised -- [0 or 1] states if layout is expanded or not
        [REGION_ID] = {w, h, x, y}
    }
}
DB[CLUSTER_ID] {
* width,
* height,
* id,
* offset_cached, -- how far into list of sources are we offset
* manual_offset_adjustment -- overlap source pools
    [PRESET_ID] = {
        preset_name,
        layout_id, (negative is from default, posative is custom)
    }

}
